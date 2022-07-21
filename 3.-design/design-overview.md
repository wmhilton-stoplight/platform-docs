---
tags: []
---

# API Design Overview

API design (also known as modeling) involves describing all the inputs and outputs across the footprint of your entire service. Your API design will answer questions like:

- What are the different resources and operations available in your API?
- How does your API authenticate requests?
- What are the different [data models](models.md) associated with your service?
- How does your API handle errors?

## API Design and Stoplight

Stoplight Studio is where you and your team will maintain the single source of truth that describes the inputs and outputs of your API. Studio provides full validation, mocking, and modeling support for OpenAPI 2 and 3.x documents.

Once you have your API described in Stoplight Studio, you can:

- Publish all or part of your API. See [Types of Documentation](../4.-documentation/b.types-of-documentation.md).
- Send requests to your API to debug it. See [Try It](try-it.md).
- Create a mock API based on your descriptions. See [Mock Servers](setting-up-a-mock-server.md).
- Validate your files with Spectral, the open-source API description linter. See [Validation and Linting](validation-and-linting.md).

## Get Started

There are a few ways to get started designing your API with Stoplight Studio:

- [Design-First Principles](https://meta.stoplight.io/docs/api-best-practices/ZG9jOjM2NTM5Nzc2-design-first-principles)
- [Models and Schemas](models.md)
- [JSON Schema Editor](json-schema-editor.md)
- [Shared Components](shared-components.md)
- [Validation and Linting](validation-and-linting.md)
- [Understand the Directory Structure](../7.-projects/working-with-files.md#directory-structure)

## Studio Web vs. Studio Desktop

Stoplight Studio is available in two different formats: desktop and web. Studio Desktop is an offline-first application that runs locally on your computer. Studio Web is a web application that runs in your browser. 

### Studio Web

The Studio Web interface is ideal for collaboration and working in real time with existing hosted Git repositories. For quick and easy publishing, you can also create web projects that aren't tied to a repository.

Studio Web is part of the larger [Stoplight Platform](https://stoplight.io/welcome) ecosystem, which provides API design and style guide editors, hosted documentation, an Explorer for searching across multiple APIs, and much more.

Learn more about [Studio Web](../a.introduction.md).

### Studio Desktop

The [Studio Desktop](https://stoplight.io/studio/) application provides an offline-first, native interface for designing and modeling your APIs. It also allows you to work directly with local files and folders on your computer.

This standalone tool can be used to edit the contents of any projects, whether or not they're linked to the Stoplight Platform. See [Local Projects](../2.-workspaces/f.working-with-local-projects.md) for details.