---
tags: [Governance]
---

# Getting started with API Governance

[API Governance]() programs are being undertaken across companies of all shapes and sizes, but that's not to say that all of them achieve their desired objectives. It is important to have a well-planned API governance initiative complemented by the right tools and inclusion of collaborators across the organization. 

To build a successful API governance program, thinking about governance in the right context is paramount. There's no single strategy that fits all circumstances and use-cases. Governance is often a balancing act and it's wise to take a light step-by-step approach. Stoplight's platform arms you with the tooling to help you at each stage of your initiative. 

While a lot of decisions would be taken in the context of your organization, these pointers can help you craft and execute your plan.

#### Identify goals

Before diving into the steps that you need to take to fuel governance in your organization, it's important to map out your API Program's objectives and issues. This could be done by conducting interviews with leaders and stakeholders in the API lifecycle. You could:

- Make an organization chart identifying stakeholders across the organization
- Understand API roadmap in terms of internal, partner and external services
- Identify issues faced by development teams
- Gather feedback from API consumers
- Identify key goals e.g. Autonomy, Agility, Control

#### Find your APIs

A recurring problem that is seen in rapidly growing API programs is not knowing where your APIs are. Not knowing what services exist or what their current status leads to duplication, inconsistencies and unanticipated disruptions. *You can't fix what you don't know is broken*. 

Create an inventory of your existing APIs. You can use the platform to [add your projects]() from version control or other file systems. Creating this central view is necessary for achieving your governance goals. It's important to get as many of the APIs as you can across your organization into this inventory. 

#### Explore your landscape

With your inventory of APIs ready, you can start gauging the current status of your API landscape. Stoplight's Platform makes it easy to visualize and rationalize your APIs. After [adding your projects]() to the Explorer you can discover:

- Existing APIs
- API contracts and the formats being used e.g OAS3, Postman, RAML
- Dependencies between endpoints, models, and articles in your organization
- State of documentation for different APIs
- Security policies being used 
- Changelogs for different versions of APIs and Schemas 

We recommend sharing this information with stakeholders using the Explorer. This information would come in handy in making governance decisions. Learn more about exploring your API landscape [here]()

#### Engage stakeholders

One of the biggest reasons for inconsistency across your API program stems from teams working in silos. Governance initiatives are most effective when all stakeholders are on board. [Adding team members]() like developers, technical writers, product managers, and business leaders into your Stoplight Platform would give them visibility to your APIs and guidelines while bridging the gap between different stakeholders. Having everyone on the same page makes your API program effective and valuable. 

#### Enforce writing API descriptions

An important discovery while exploring your API landscape is the current state of API descriptions being used in your organization. API descriptions have become an industry-wide practice and are something that should be pushed as mandatory in any organization. You should:

- Enforce creating and updating API descriptions for all existing APIs. [Stoplight Studio] is a powerful tool to start creating and managing your designs. 
- Converge teams on a single API description format. We recommend moving to OAS due to its extensive support and adoption. 

#### Create style guidelines 

It's important to standardize your API design to ensure consistency across your APIs. You can start that by [creating style guides]() in Stoplight that can be used to validate your API designs. 

While the goal is to have one set of enterprise-wide API governance rules, your learnings from previous steps would help you take a prudent step-by-step approach to this. Gauging what your teams are already doing, start converging them on a set of rules. You can start with a combination of mandatory rules and optional guidelines to help folks make better decisions. 

Examples of rules that you can apply:

- Naming conventions
- Mandatory descriptions for all artifacts
- Mandatory security for all paths
- Only use a type of OAuth as the security scheme

Learn more about [Style Guides]().

#### Create a Design Library

Often developers without access to existing resources end up creating duplicate code that leads to inconsistencies and maintenance nightmares. You need to identify reusable design components and put them in a central repository. You can do this by [creating a design library] in the Stoplight Platform. This can then be used in APIs across your organization.   

#### Enable API discovery

As the number of APIs in your portfolio grow folks need to have an easy way to discover your APIs. You should publish your APIs at a central hub with search capabilities for your API consumers.

Using the Stoplight platform you can:

- [Create a Hub] where teams can publish their APIs for internal and external consumption.
- Add team members to your workspace to help them keep a track of dependencies using explorer. 

#### Promote Design-first for new APIs

While enforcing API descriptions for your existing APIs is helpful, the true power of API descriptions is realized by following an [API Design-First]() policy. Designing your APIs before development helps you get quick feedback, develop in parallel and test automatically. Help your architects get started with a new API design by sharing this [guide](). 

#### Implement versioning

APIs often need modifications or sometimes deprecating, and versioning is therefore crucial. It’s important to apply your governance rules to ALL the versions, to ensure they’re all standardized and properly documented. You can use Explorer to visualize changes between different versions, helping you intelligently manage breaking changes.

#### Automate your governance process

Having to rely on your teams to manually apply your API governance rules is no fun for anyone, and not feasible when you’re developing APIs at scale. Ensure your API governance rules are met before an API can be deployed. Deploying APIs with governance violations even internally is not recommended.

Stoplight Platform makes this easy along the lifecycle using:
- Automatic Style Guides
- Contract Testing powered by automatic mock servers

#### Analyze and improve

Governance is an ongoing initiative. Explorer provides you with a bird's eye view of your landscape that can help you identify gaps and gauge improvements. As you learn from your experiences and add to your initiatives, it helps to:

- Get more stakeholders on board
- Evangelize about your APIs and governance initiatives 
- Gather feedback
