---
tags: [Design]
---

# Overview

Stoplight has an editor called Studio, which can help you write Markdown, but more importantly it's a visual API Designer, with built in support for working with API Descriptions, with support for the most popular format: OpenAPI (both v2 and v3). 

## What is an API Description

API Descriptions usually take the form of a YAML or JSON document which can explain the "I" part of API: the interface. This covers HTTP methods, endpoints, headers, authentication schemes, request bodies, example responses, and every other part of an API, including callbacks and webhooks!

For years folks would be stuck writing this YAML or JSON by hand in a text-editor, but API Design software like Stoplight Studio aims to make that be a thing of the past, providing a graphical interface that reduces the redundancy of working with plain text. 

## API Design-First

API descriptions can be created before you build an API, or afterwards. In ye olden times, people would build a whole API, put it into production, then think "oh I should probably write some documentation." You can do that with Studio if you like, but there is another way.

API Design-First is the concept of planning out the API before you build it, and instead of doing that in some Google Document or on the back of a napkin, you can do it in a reusable, machine readable format which can power functionality at every stage of the API lifecycle:

1. Generate Documentation - beautiful API reference documentation
1. Mock Servers - early API consumer feedback
1. Request Validation - why write all those rules twice
1. Contract Testing - ensure API is doing its job
1. Code Generation - computers have learned to program themselves
1. SDK Generation - let API consumers talk their programming language of choice

When an API has been designed up front, API consumers have had a chance to play with a mock server, the protoype has been built and feedback is good, you can build the API with confidence that it's matching the plan thanks to contract testing. 

Catching potential problems for clients early on avoids wasting time and money writing code which is not going to solve a problem. It also reduces the chances of noticing major issues shortly after v1.0 launches, meaning you can put off v2.0 and v3.0 for a while, maybe indefinitely.

<!-- TODO refactor functionality can talk about ## API Design-Catchup -->

## Stoplight Studio

Stoplight Studio comes in two flavours:

- Studio Web - A module available as part of Stoplight Platform
- Studio Desktop - A downloadable desktop application for offline use, supporting MacOS, Windows and Linux

They both do the same job: help you create and modify content in your workspace's projects, and push changes back. Stoplight Studio choses to do awak with awkward two-way syncs introduced by some tools, and stick to tried and tested Git-based workflows.
