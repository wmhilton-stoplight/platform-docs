---
tags: [Design]
---

# Starting a new API design

Following the [API Design-first](./a.overview.md#API-Design-First) workflow, the first step to making a new API would be to send out a survey asking customers: 

- What are the key business needs and workflows you are trying to solve?
- What existing APIs are you talking to, if any?
- What platform will you be creating this for, mobile, web, backend?
- What data will you keep copies of locally, vs referencing from the API?

The responses to these questions will get me thinking about how an API needs to function, and knowing what sort of clients we're primarily dealing with can help think about the size of payloads. 

For example, if it's primarily backends and web apps and HTTP/2 multiplexing is an option, the API will contain more endpoints with smaller payloads, whereas mostly mobile clients could be be better off with a smaller number of slightly larger calls.

## Explore What Already Exists

With those answers in place, the next step is to think about the resources that need to exist. 

We need a "Passenger" resource, so search for an existing "Passenger" model.

We need a "Flight" resource, so search for an existing "Flight" model.

If you find some shared models that describe roughly how you think your resource should look then great, you've saved yourself some work! Click the Star, and we can use them later.

## Designing the Interface

The next step is to open up Stoplight Studio, to create a new Project. In here we can add a new API, give it a name, and start ...

<!-- Take higher level content from https://stoplight.io/blog/getting-started-with-api-design-using-stoplight-and-openapi-90fc8f37ac2e/ -->

## Linter Guidance

Make sure standards are being followed. Check for warning, errors.

## Plan Documentation

Plan documentation (Pointers for tech writers)
