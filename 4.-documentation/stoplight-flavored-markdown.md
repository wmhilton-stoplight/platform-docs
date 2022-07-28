# Stoplight Flavored Markdown (SMD)

Stoplight Flavored Markdown can be used to enhance existing Markdown documentation with necessary documentation components like code blocks, images, diagrams, and more.

The Two Laws:

1.  SMD is human readable. A human with a simple text editor can easily read and write SMD.
2.  SMD degrades gracefully. SMD documents rendered on `github.com` should be clean and readable.

The Approach:

1.  Stoplight Flavored Markdown extends GitHub Flavored Markdown with inline comment annotations.
2.  The value inside of the annotations is a YAML object, and the annotation affects the Markdown block that directly follows it in the document.

By leveraging comments to store annotations, Stoplight Flavored Markdown degrades gracefully to any other Markdown renderer (GitHub, for example).

## Headers

Stoplight uses levels H1 to H3 to automatically populate the in-page navigation, as shown in the following example. H1 and H2 display at the main level; H3 is nested under H2.

![In-page Navigation](../assets/images/in-page-navigation.png)

## Callouts

A callout is an Markdown blockquote with an optional annotation that indicates intent.

### Danger

<!-- theme: danger -->

> #### Danger Will Robinson!
>
> Here is a danger callout!

```md title="Copy this code to try it out!"
<!-- theme: danger -->

> #### Danger Will Robinson!
>
> Here is a danger callout!
```

### Warning

<!-- theme: warning -->
> #### Watch Out!
>
> Here is a warning callout!

```md title="Copy this code to try it out!"
<!-- theme: warning -->
> #### Watch Out!
>
> Here is a warning callout!
```

### Success

<!-- theme: success -->

> #### Mission Accomplished!
>
> Here is a success callout!

```md title="Copy this code to try it out!"
<!-- theme: success -->

> #### Mission Accomplished!
>
> Here is a success callout!
```

### Info

<!-- theme: info -->

> #### A thing to know
>
> Here is an info callout

```md title="Copy this code to try it out!"
<!-- theme: info -->

> #### A thing to know
>
> Here is an info callout
```
## Task Lists

- [ ] one
- [x] two
- [ ] three

```md title="Copy this code to try it out!"
- [ ] one
- [x] two
- [ ] three
```

## Code Blocks

An SMD code block is an Markdown code fence with an optional annotation to tweak the presentation of the code block.

**Supported annotations**:
- **title**: Title for the code snippet
- **lineNumbers**: True/False to toggle line number visibility

### Markdown Annotations
<!--
title: "Code snippet passed via Markdown annotations"
lineNumbers: true
-->

```javascript
function fibonacci(num) {
  var a = 1,
    b = 0,
    temp;

  while (num >= 0) {
    temp = a;
    a = a + b;
    b = temp;
    num--;
  }

  return b;
}
```

```example title="Try out the annotations!"
<!--
title: "My code snippet passed via Markdown annotations"
lineNumbers: true
highlightLines: [[1,2], [4,5]]
-->
```

### Meta Tag Annotations

You can also pass the annotations via the code block meta tag.

```json title="Passed via meta tag" lineNumbers
{
  "foo": "bar"
}
```

```example title="Try the annotations out!"
json title="Passed via meta tag" lineNumbers
```

## Code Groups

If you write multiple code blocks with no other content between, they're grouped into a tabbed code group. This is helpful for a variety of use cases, such as displaying code samples in a variety of languages.

<!-- theme: warning -->

> Note that code groups can't be nested in other elements like tabs.

```js title="Code groups work with titles and other annotations!" lineNumbers
// Install via npm
npm install --save my-library
```

```ruby title="Lovely isn't it?"
# Available as a gem
sudo gem install my-library
```

```php title="Enjoy!"
# Install the PHP library via Composer
composer require my-library
```

## Images

Use annotations to frame up product images.

**Default**

The default setting adds an outline and "click-to-zoom" for images. 

![Stoplight Logo](https://stoplight.io/images/home/logo-blue-black.png)

```md title="Try it out!"
![Stoplight Logo](https://stoplight.io/images/home/logo-blue-black.png)
```

**Center Focus**

Make screenshots pop out with a center focus and a default background image. 

<!-- focus: center -->

![Docs portal settings](https://i.imgur.com/YCb6MWI.png)

```md title="Try it out!"
<!-- focus: center -->

![Docs portal settings](https://i.imgur.com/YCb6MWI.png)
```

**Add a Caption**

Add an optional caption to further explain the screenshot. 

<!-- focus: top -->

![Studio project share](https://i.imgur.com/ueOOL8X.png 'Can add an optional caption')

```md title="Try it out!"
<!-- focus: top -->

![Studio project share](https://i.imgur.com/ueOOL8X.png 'Can add an optional caption')
```

**Try a Different Background Color**

<!--
focus: top
bg: primary
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png)

```md title="Try it out!"
<!--
focus: top
bg: primary
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png 'Can add an optional caption')
```

**Use a Hex Background Color**

<!--
focus: top
bg: "#f78ae0"
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png)


```md title="Try it out!"
<!--
focus: top
bg: "#f78ae0"
-->

![Studio project share](https://i.imgur.com/ueOOL8X.png)
```

**Good Old Plain Images**

<!-- focus: false -->
![Studio project share](https://i.imgur.com/ueOOL8X.png)


```md title="Try it out!"
<!--
focus: false
-->
```

## Graphs and Diagrams

You can add graphs and diagrams in your Markdown using [Mermaid syntax](https://mermaid-js.github.io/mermaid/#/flowchart). Mermaid supports common UML diagrams, such as sequence diagrams, class diagrams, state diagrams, ERDs, User Journey, Gantt, pie charts, and more. 

Wrap any Mermaid syntax with a `mermaid` code block. 

<!-- theme: warning -->

> Note that diagrams can't be nested in other elements like tabs or code groups.

### Flowchart

```mermaid
graph TB
    c1-->a2
    subgraph ide1 [one]
    a1-->a2
    end
```

```example
graph TB
    c1-->a2
    subgraph ide1 [one]
    a1-->a2
    end
```

### Sequence

```mermaid
sequenceDiagram
    autonumber
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

```example
sequenceDiagram
    autonumber
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

### Journey

```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```

```example
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```

## JSON Schema

The SMD JSON schema block is a Markdown code block with an additional `json_schema` language tag. The contents of the code fence should be the JSON schema object to be rendered. The primary language tag can be `YAML`, `YML`, or `JSON`.

```json json_schema
{
  "title": "User",
  "type": "object",
  "properties": {
    "id": {
      "type": "string"
    },
    "name": {
      "type": "string",
      "description": "The user's full name."
    },
    "age": {
      "type": "number",
      "minimum": 0,
      "maximum": 150
    }
  },
  "required": ["id", "name"]
}
```

Try it out with the example below:

````json title="Try it out!" 
```json json_schema
{
  "title": "User",
  "type": "object",
  "properties": {
    "id": {
      "type": "string"
    },
    "name": {
      "type": "string",
      "description": "The user's full name."
    },
    "age": {
      "type": "number",
      "minimum": 0,
      "maximum": 150
    }
  },
  "required": ["id", "name"]
}
```
````

### Embed Models

You can also use JSON Schema to embed a model from your API description in a Markdown article by using the `$ref` property:

````yaml title="Embed model" 
```yaml json_schema
$ref: "../models/user.yaml"
```
````

## Try It

### Basics

Writing a `json` code block with the `http` tag added displays a **Try It** component.

You must provide `method` and `url` parameters:

````json
```json http
{
  "method": "GET",
  "url": "https://todos.stoplight.io/todos",
}
```
````

This results in the following component being displayed:

```json http
{
  "method": "GET",
  "url": "https://todos.stoplight.io/todos",
}
```

### Optional Parameters

There are also optional parameters that you can provide to the component. 

`query`, `headers`, and `body` parameters allow you to create a Try It component that supports sending requests with a query, header, and/or body content. Users can fill and edit those contents and then send the request.

So, for example, to use `query`, `headers` and `body` all at the same time, write:

````json
```json http
{
  "method": "POST",
  "url": "https://todos.stoplight.io/todos",
  "headers": {
    "Content-Type": "application/json"
  },
  "query": {
    "name": "query value"
  },
  "body": {
    "some parameter": "some value"
  }
}
```
````

This results in the following component:

```json http
{
  "method": "POST",
  "url": "https://todos.stoplight.io/todos",
  "headers": {
    "Content-Type": "application/json"
  },
  "query": {
    "name": "query value"
  },
  "body": {
    "some parameter": "some value"
  }
}
```

If you prefer, you can use the `baseUrl` parameter, which allows you to write the following. This doesn't affect the functionality, but can be used for improved readability.

````json
```json http
{
  "method": "GET",
  "url": "todos",
  "baseUrl": "https://todos.stoplight.io",
}
```
````

## Tabs

An SMD tab container is a `tab` annotation, followed by the tab content, and closed by a final `tab-end` annotation.

<!-- theme: danger -->

> Tab containers can't be nested.

<!--
type: tab
title: My First Tab
-->

The contents of tab 1.

<!--
type: tab
title: My Second Tab
-->

The contents of tab 2.

<!-- type: tab-end -->

```md title="Try it out!" 
<!--
type: tab
title: My First Tab
-->

The contents of tab 1.

<!--
type: tab
title: My Second Tab
-->

The contents of tab 2.

<!-- type: tab-end -->
```

## HTML

Most basic HTML is supported. **However, use the Markdown equivalent whenever possible.**
<table>
  <thead>
    <tr>
      <td>heading 1</td>
      <td>heading 2</td>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>hello</td>
      <td>world</td>
    </tr>
  </tbody>
</table>

---

## Embeds

Stoplight supports embedding a variety of content from popular websites. To use an embed, write out a link in its own paragraph.

For example, this is a YouTube video:

https://www.youtube.com/watch?v=VbSPeYo8dfM

```md title="Try it out!" 
https://www.youtube.com/watch?v=VbSPeYo8dfM
```

This is a Giphy gif:

<!-- markdown-link-check-disable -->

https://giphy.com/gifs/barkpost-barkpost-happy-wednesday-working-like-a-dog-eYilisUwipOEM

```md title="Try it out!" 
https://giphy.com/gifs/barkpost-barkpost-happy-wednesday-working-like-a-dog-eYilisUwipOEM
```

<!-- markdown-link-check-enable-->

Stoplight also supports audio:

https://open.spotify.com/episode/7jobY4wQXnt1T0E9iwVRte

```md title="Try it out!" 
https://open.spotify.com/episode/7jobY4wQXnt1T0E9iwVRte
```

<!-- markdown-link-check-disable -->

### Supported Websites

- Coding
  - [GitHub Gist](https://gist.github.com)
  - [CodeSandbox](https://codesandbox.io)
  - [Codepen](https://codepen.io)
  - [Runkit](https://runkit.com)
  - [Replit](https://replit.com)

- Video
  - [YouTube](https://www.youtube.com)
  - [Vimeo](https://vimeo.com)
  - [Grain](https://grain.co)
  - [Giphy](https://giphy.com)

- Audio
  - [Spotify](https://www.spotify.com)
  - [SoundCloud](https://soundcloud.com)

- Design
  - Figma
  - [Slideshare](https://www.slideshare.net)
  - [SpeakerDeck](https://speakerdeck.com)

- Social
  - [Twitter](https://twitter.com)
