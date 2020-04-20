---
tags: [Governance]
---

## Style Guides

Ask 100 developers where a semicolon should go, and you'll either get 100
answers, or a all-on-all fist fight. To save this from happening most
API teams that grow beyond a handful will implement a style guide.

Also known as API Design Guides, Design Guidelines, Style Books, or API Standards, the concept of "make a bunch of decision's and write them down" has helped API teams for decades.

These style guides might contain rules about how to handle versioning, filtering, error formats, naming conventions, pagination, or any of a million other variable parts of an API which different teams would likely make different decisions on.

### Where Style Guides Live

Some companies will write these down as Google Documents, an internal Wiki, maybe they're an example API description document somewhere with comments and examples. 

Sometimes these get published, which can give useful insight into what big companies and government organizations consider to be a "good API" for them. [API Stylebook.com > Design Guidelines](http://apistylebook.com/design/guidelines/) is a collection of these style guides.

The trouble with these text-based documents is that they are large, terse documents which developers rarely read. If developers _do_ read them cover to cover, _and_ remember everything in there, that knowledge becomes partially out of date when new rules are added because they won't know about them until they re-read everything cover to cover again.

These days style guides can be automated by programming rules into a format which robots can understand:

- [Spectral](https://stoplight.io/open-source/spectral/) by [Stoplight](https://stoplight.io/)
- [api-linter](https://github.com/googleapis/api-linter) by Google
- [graphql-schema-linter](https://github.com/cjoudrey/graphql-schema-linter) by [Christian Joudrey](https://twitter.com/cjoudrey)

We've built Spectral to be as flexible as possible for any type of JSON/YAML-based data, which includes built-in rules for OpenAPI, AsyncAPI, JSON Schema, but also means you could write custom rulesets for RAML, Kubernetes config, or anything else written in JSON or YAML.

### Example Rules

Running Spectral CLI on OpenAPI files will be default use the [OpenAPI Ruleset](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/reference/openapi-rules.md). This ruleset will offer various suggestions which can be helpful for developers not entirely familiar with OpenAPI. 

For example, adding contact information to the API description is often overlooked, but massively useful for people who have questions about the API later.

```
openapi: '3.0.3'
info:
  version: 1.0.0
  title: PokeAPI
  license:
    name: MIT
paths:
  ...
```

<!-- theme:warning -->

This will trigger a warning:

> Info object should contain `contact` object

Another handy rule is catching out copy-and-paste mistakes like reusing an operationId between multiple operations. Seeing as many tools use this for unique URLs, and some code generators even use these to create function names, catching this out can solve a lot of confusion later.

```yaml
paths:
  /pet:
    patch:
      operationId: "update-pet"
      responses: 
        200:
          description: ok
    put:
      operationId: "update-pet"
      responses: 
        200:
          description: ok
```

Spectral will give anyone repeating an operationId a warning: 

<!-- theme:warning -->

> Every operation should have a unique `operationId`.

Spectral avoids enforcing any opinions about the actual API being designed, but it's absolutely supported.

Custom Rulesets can be used with rules that look at the values of the URIs, header names, etc. too. 

### Custom Rulesets with Spectral

[Rulesets](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/getting-started/rulesets.md) is the term we use for a collection of Rules, which is essentially going to be your automated style guide. Each rule is one bit of style you'd like to enforce.

You can do pretty much anything with a ruleset, by using our built-in functions, or get more powerful with [custom functions](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/custom-functions.md)!

Stoplight Platform, Studio, Spectral, etc will all look for a `.spectral.yaml` (could be `.json`) which contains a rules object. 

If I want to enforce all operations (API endpoints) are kebab-case `/berry-flavor/` instead of camelCase `/berryFlavour` or some other case, we could do that.

```yaml
# .spectral.yml
rules:
  paths-kebab-case:
    description: Should paths be kebab-case.
    message: '{{property}} is not kebab-case: {{error}}'
    given: $.paths[*]~
    then:
      function: casing
      functionOptions:
        type: kebab
        separator:
          char: "/"
```

Want to stop people using `X-Foo` headers? Block it for all headers everywhere with the built-in `notMatch` function.

```yaml
rules:
  no-x-headers:
    description: "Please do not use headers with X-"
    message: "Headers cannot start with X-, so please find a new name for {{property}}. More: https://tools.ietf.org/html/rfc6648"
    given: "$..parameters.[?(@.in === 'header')].name"
    then:
      function: pattern
      functionOptions:
        notMatch: '^(x|X)-'
```

Done early enough, this will shape the actual API as it is being developed. The ruleset will come into effect in Studio, so that as people are typing they get feedback if they break a style guide rule. 

<!-- todo show spectral off in studio web -->

If you're a code-first team then this is less ideal, as you'll potentially need to change code which exists in production just to get it to match this style guide.

[Custom functions](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/custom-functions.md) can be created for more advanced use cases. Maybe you want to implement a dictionary check to ban British spelling of words like "flavour" - that should _of course_ be "flavor". 😅

#### Automation

Seeing as Spectral is a JavaScript library wrapped in a CLI, enforcing this style guide can be done in all sorts of ways.

- in [a git hook](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/1-workflows.md#git-hooks)
- in a JavaScript test suite using the [JS API](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/3-javascript.md)
- on [continuous integration](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/1-workflows.md#continuous-integration) to fail builds with errors

#### Distributing Rulesets

Rulesets can just be defined as a file in a repository, but that will lead to every API having their own different rules, which somewhat defeats the purpose.

One approach is to publish your ruleset to a publicly available URL, then folks can extend it in their repo:

```yaml
extends: https://example.com/api/spectral.yaml
```

Alternatively, especially if you need [custom functions](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/5-custom-functions.md), you can [publish a ruleset as a NPM module](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/7-sharing-rulesets.md#NPM).

```yaml
extends: example-npm-ruleset
```

Pegging a ruleset on given version can be done in the following manner:

```json
{
  "extends": ["example-npm-ruleset@1.0.4"]
}
```

#### Evolving Rulesets

New rulesets can be added as your style guide evolves, as new problems occur and new standards need to be met.

For example, the API Governance team decides that all APIs need to be running on HTTPS, and only HTTPS. No HTTP allowed anywhere in the company. They could add this rule:

```yaml
  oas2-hosts-https-only:
    description: "ALL requests MUST go through `https` protocol only"
    severity: info
    formats: [oas2]
    message: "Schemes MUST be https and no other value is allowed."
    given: $.schemes
    then:
      function: schema
      functionOptions:
        schema:
          type: array
          items:
            type: string
            enum: ["https"]
          maxItems: 1
```

As the severity is just `info` this will show up in Studio, be output by Spectral CLI, and show up in continuous integration results, all without causing any problems. It's just an informative message, that folks should notice and tweak as they go.

A few weeks or months later when you know most people have implemented this change, you can bump up the severity in order to get the slackers to do the work. 

```yaml
  oas2-hosts-https-only:
    description: "ALL requests MUST go through `https` protocol only"
    severity: warn
    # ...
```

This change will start to show up in Studio as a warning, which will also fail Spectral CLI and trigger a failed build in any Continuous Integration running it too. 

Doing this at the right time for the right reason is a powerful tool to communicate change across large organizations, but using this too heavy handedly can be a problem.

If there are any problems (like hotfixes cannot go out because of CI failures) then anyone can disable rules for specific resources using a feature we call [Exceptions](https://stoplight.io/p/docs/gh/stoplightio/spectral/docs/guides/6-exceptions.md): 

```yaml
extends: spectral:oas

except:
  "one.yaml#":
    - oas3-api-servers
  "./one.yaml#/info":  # Beside relative ones, also supports rooted paths ;-)
    - info-contact
```


If you already have a style guide, see how much of it you can solve with the build-in functions, then start to get more creative with custom functions to solve the organizations biggest issues. 

Whether you focus on quality, consistency, or security, and whether you write rules for the API description document, the API implementation itself, or both, see how much you can get done before resorting to writing things up on a wiki. 

We're hoping its most of it. 

### Ideas

Here are some ideas for things you can write rules for:

### Security

- Ban HTTP Basic entirely
- Make sure every endpoint has some sort of security (OAuth 2, API Key, but not both)
- Every response should support `application/vnd.api+json` ([JSON:API](https://jsonapi.org/)) not just plain-old JSON
- ID's as integers let people [crawl your API](https://phil.tech/http/2015/09/03/auto-incrementing-to-destruction/) incredibly easily, switch to UUID

#### Errors

- Your `20X` response seems to have errors in it, which is confusing
- There are no URLs in your errors, how can anyone find out more information about what went wrong?
- Error format should be [RFC 7807](https://tools.ietf.org/html/rfc7807)

#### Versioning

- Keep [version numbers out of the URL](https://apisyouwonthate.com/blog/api-versioning-has-no-right-way/)
- Version numbers in headers please
- Ban all versioning and [demand evolution](https://apisyouwonthate.com/blog/api-evolution-for-rest-http-apis/) (prepare for battle)
