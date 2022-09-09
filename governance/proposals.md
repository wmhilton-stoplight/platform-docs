---
stoplight-id: jmirdp5mkp3xj
---

# Proposals

---

<!--
focus: false
-->
![Feature Preview](../assets/images/badge-preview-small.png)

We're committed to providing the best API experience for our users. This feature is being actively improved and you can help by [providing feedback](https://docs.google.com/forms/d/e/1FAIpQLSeW24zIlv0jUgrxrFmIlssk7YDaA_NMYVJVs75_TuEUsM8tYA/viewform).

---

**Proposals** automatically surface in-flight API design and documentation changes across all Git-connected projects in your workspace.

Proposals facilitate oversight + governance  oversight within your API program by:

- **Increasing Visibility**: The proposals screen provides a single point of access that surfaces all in-flight API Design and Documentation changes across the Git-connected projects in your workspace.
- **Mitigating Risk**: Proposals highlight potentially [breaking changes](#about-breaking-changes) to your API.
- **Surfacing Affected Consumers**: Ever wonder which API operations are affected by the removal of that one shared schema property? Proposals is `$ref` aware, making it easier to understand the true impact of changes to shared components.

**Limitations**

> These are known limitations that we plan to address in the future.

1. Remote `$refs` aren't resolved, so proposals won't include changes made to references to resources that exist outside of a project. 
2. Changes aren't tracked for `toc.json`, `.stoplight.json`, `.spectral.json`, and binary images.  
3. Proposals aren't available for Stoplight web projects (those not connected to Git).
4. Articles with images stored in Git don't render correctly.
5. Article-to-article links don't resolve correctly.

## View the Proposals List

Proposals are available for users who have the **Makers** role. Internal and public projects are listed. Private projects are only included for users who can view those projects. 

To see the list of proposals:

1. Log in to your workspace.
2. Select **Proposals** from the workspace left sidebar.

## Create a Proposal

Proposals are created automatically for Git branches that contain changes to API Design or Documentation files, when compared to their baseline Git branch.

On the proposals list, use the **State** dropdown to filter proposals by:

* **All**: Shows all Git branches that contain API design or docs changes vs. their baseline branch (effectively, a "Proposal").
* **Review**: Proposals that have an associated open pull request.
* **Feedback**: Proposals that have an associated open draft pull request.
* **Work in Progress**: Proposals without an associated pull request. This can occur if you create a new Git branch in Studio and push some changes to your design files, but haven't yet opened a pull request in your VCS.

![Proposal](https://stoplight.io/api/v1/projects/cHJqOjI/images/sCjrQq3oCSg)

For each proposal, you can see:

1. The name of the project.
2. The name of the branch that contains proposed changes and the state of the branch.
3. Information about the proposal, including a summary of the changes, the composition of the changes (operations, schema, or article), and when the last change was made and by whom.
4. [Breaking change](#about-breaking-changes) indicator, if they're found. 

Once a branch is merged or deleted, it's removed from the **Proposals** list.

## The Proposals Page

To review a proposal:

1. Select **Proposals** from the workspace sidebar.
2. Select the proposal you want to review.

![Proposals Page](https://stoplight.io/api/v1/projects/cHJqOjI/images/SXvlkvmJJr0)

### `A` Branches and Pull Requests

See the originating branch and the working branch for each proposal. You can also open an existing pull request for a proposal. If there is no pull request, the main repository page opens. 

### `B` List of Proposed Changes 

Contains a list changes in a branch. You can see which files were added, updated, deleted, or contain [breaking changes](#about-breaking-changes). Files are organized by articles and APIs. API changes include the overview, operations, and schemas. 

> When you change a schema that's referenced in operations or other schemas, impacted files are included in the change list so you can see the impact of the schema change.

### `C` Change View

Select one of three views for each change:

* **Text Diff**: See line-by-line changes for a selected file.
* **Current**: See the latest update in the branch.
* **Previous**: See the version of a file from the branch creation.

### `D` Change Details

Select a file from the left pane to see details for each change in the right pane. You can also see the **affected consumers**, which shows the  operations and schemas impacted by a change. 

## About Breaking Changes

Stoplight will flag certain changes to APIs and schemas as potentially breaking changes. Breaking changes typically require API consumers to modify their implementations, so it's important to be aware of breaking changes before you approve and deliver updates to your API. 

Once you understand breaking changes in your proposal, you can:

* Remove them from your API.
* Create a new version of the API so that older versions remain backwards compatible with existing implementations.
* Inform API consumers of the breaking change and provide steps for updating implementations to accommodate the change.

Examples of breaking changes include:

* Removing an operation that may be in use
* Adding a required request parameter without setting a default value
* Removing an enum value from a list of allowed values

### Breaking Change Reference

<!--
type: tab
title: Global
-->

**Removing**
- http service
- http operation
- http server

**Modifying security scheme**
- type
- in
- scheme
- bearerFormat
- openIdConnectUrl

**Modifying server**
- url

<!--
type: tab
title: Operations
-->

**Adding**
- http operation security

**Modifying**
- method
- path
- setting internal = `true`

<!--
type: tab
title: Requests
-->

**Adding**
- a required request parameter (query, header, cookie, path)
- a required property to the request body

**Modifying request body**
- required = `true`

**Modifying request parameters**
- name
- style
- required = `true`
- allowEmptyValue = `false`
- allowReserved = `false`

<!--
type: tab
title: Responses
-->
**Removing**
- a required response parameter (header, cookie)
- a required response schema property

**Modifying**
- code

<!--
type: tab
title: Schemas
-->
**Modifying schema properties**
- type
- enum: adding it, when it wasn't set before
- enum: removing a value from existing list of allowed values
- format
- maxItems, maxContains, maxProperties, maximum, exclusiveMaximum, maxLength: if previously set and the new value is smaller than the previous value
- minItems, minContains, minProperties, minimum, exclusiveMinimum, minLength: if previously set and the new value is larger than the previous value
- uniqueItems = `true`
- multipleOf
- pattern

**Modifying schema properties, in the context of a request**
- required = `true`

**Modifying schemas, in the context of a response**
- required = `false`

<!-- type: tab-end -->