---
tags: [Developer Experience]
---

# Overview

Good developer experience is the key to a useful, usable API. An API could be all-powerful, solving a problem and sublimely implemented, yet it won't matter one bit if users,  internal or external, can't figure out how to make it work. The aggregate experience of the user **discovering**, **learning to use**, and finally **integrating** with an API is termed as Developer Experience (DX). Developer Experience (DX) is the equivalent to User Experience (UX) for your APIs.

### Why does it matter?

DX matters for the same reasons that good UX matters. Users of your API are happier, promote it more, and stay longer when the API has good DX. Your API is a means to an end for the user, and they want to integrate as quickly as possible to move forward in their product development, meaning **they should immediately understand the value and usage of your API**.

### Components of Good DX

1. **A good/consistent API design**

We can't stress this enough; **no amount of documentation can make up for a poorly designed API**. If you haven't already, read more about [designing APIs](../3.-design/a.overview.md). 

2. **Your Audience**

The users of your APIs are primarily two kinds of people:

The **decision-makers** who discover and decide if your API is a good fit to fulfill their use-case. They can be CEOs, CTOs, Product Managers, or Business Executives. 
 
The **developers** who interact with the API to fulfill the use-case. These developers can be internal or external and novice or experienced. Novice developers would usually require more hand-holding while experienced devs would frequently be using your API docs as a reference. 

Your developer experience must cater to both kinds of consumers. You want them to **decide and integrate with ease**. 

3. **API Reference**

An accurate, up-to-date, and detailed API reference is one of the essential pieces of your developer experience. An API reference contains:

- Authentication information
- Endpoint descriptions, parameters, and responses
- Example requests and responses
- Models
- Error messages

4. **Test environment**

Novice developers and non-technical users get up to speed faster by experimenting more than reading. Providing your consumers with a playground inside your documentation is paramount to show them value quickly. It's best to provide them with a sandbox/mock environment that's ready to use.

```json http
{
  "method": "get",
  "url": "todos.stoplight.io/todos"
}
```

5. **Code Samples**

Stack Overflow is a developer's best friend for a reason. Most developers want to jump right into code, so providing them with ready to use samples in their language can lead to happy developers saying wonderful things about you and your API. This also helps avoid mistakes novice developers can make consuming your API - Happy and smaller support teams ;)

```python
import stoplight

stoplight.create_amazing_dx()

print('Happy developers')
```

6. **Marketing Pages**

Marketing pages are for the business audience. You want these to be high level and clearly show the value your APIs can provide. Focus on the use cases businesses are trying to solve with your API and avoid technical jargon as much as you can. 

7. **Quick Start Guides**

The API reference with code samples is excellent for developers in the later stage of integration. For a newcomer starting with your API, you want to make it easy for them to navigate to creating their first integration. Developers learn best by doing. Create a quick start guide with the minimum steps required to perform the first action with your API. This can be a step-by-step guide on authentication, calling your most straightforward endpoint fulfilling the most common use case. Do not forget the code samples for these steps, and keep it easy.  

8. Tutorials

While your API is used by developers to fulfill many use cases, there are always some that are more popular. It's best to identify those and create a tutorial for them. The description of steps should be easy to follow and concise. Clarity and brevity support the learning process and are a best practice for all kinds of documentation. It's also useful to create a sample application that you can add to GitHub. 

9. Changelog

The Changelog section of your API documentation lets your users know how stable your API is. It also lets them know if anything's changed, in the instance that one of their calls stops working. These are also very helpful for existing users migrating to a newer version of your API. You can take a look at [GitHub's changelog](To-Do: Link to GitHub Changelog) for an example of thorough changelog documentation. Stoplight Platform automatically generates changelogs for your Artifacts that can be used to keep these up to date. We'll talk about this in detail later. 

10. **Terms of reference**

Terms of Use are the legal agreement between you and your users. In the Terms of Use section of your API documentation, you should include API limits, constraints, branding guidelines, and what usage is acceptable. Transparency goes very well with users, especially technical audiences. Developers love knowing everything. So, be very clear in what the terms and conditions are, avoiding putting these critical points in fine-print. 

11. **Status Page**

It's never pretty for developers trying to interact with your API and facing errors that they can't put a reason to. Being clear about the current status of your service is very helpful. You can use a service like [Statuspage]() to create one or build it yourself and make it part of your DX offering. 

12. **SDKs**

With your previous steps sorted, it always helps to reduce the redundant tasks that a developer needs to perform. For that, providing SDKs in popular languages helps keep your developers happy and productive. With your OpenAPI spec designed and validated by the powerful Stoplight tooling, you can use this to generate and publish SDKs without much extra work. We'll stick to our promise of not locking you down in our platform and letting you use all the fantastic tooling out there. 

Ready to get started with checking these boxes with Stoplight? [Get Started](b.getting-started-developer-experience.md)

### Make your APIs discoverable

Well, if the right people can't find your API documentation easily, there's not much use of having a fantastic developer experience. For internal APIs, you should use the Explorer to allow your internal users to find, analyze, and search your APIs. Star the important ones to make them easily accessible. 
 
For your External APIs to be discoverable, [create a Hub](). 