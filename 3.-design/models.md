---
tags: []
stoplight-id: 3d00f2e0c2196
---

# Models and Schemas

Schemas define data structures for an API. In Stoplight, the [JSON Schema Editor](json-schema-editor.md) provides an easy way to build OpenAPI Schema Objects.

Models allow you to describe common data structures (for example, a User object), and can contain schemas, examples, and x-extensions. Models allow for reusability. Depending on how you create models, you can reuse them in a single API, in all APIs in a project, and in all APIs across a workspace (with design libraries). See [Shared Components](shared-components.md#shared-models) to learn how to share models once you've created them.

## Add Models in a Single Project

Use this method to create models that contain data you need to share across a single API or all APIs in a project. 

1. Edit an API project.
2. Select the **Add** icon (+) at the top of the left pane, and then select **Model**.

![Add Model](https://stoplight.io/api/v1/projects/cHJqOjI/images/63LetMtnQb8)

3. On the **New Model** dialog:
    * Provide a **name** for the model.
    * Add **tags** to organize your models. See [Endpoint and Modeling Odering Rules](../4.-documentation/Sidebar/d.table-of-contents.md#endpoint-and-model-ordering-rules) for details.
    * For **Scope**:
        * Select **Common** to create a model that can be used for all APIs in the project.
        * Select **Single API** to create a model for a single API in the project, and then select the API.
    * New models are created as YAML by default. To create a JSON-formatted model, select **Show Advanced**, and then select JSON.
4. Select **Create + Add More** or **Create**.
5. Use the [JSON Schema Editor](json-schema-editor.md) to build a schema object and examples.

> You can also right-click on the **model** or **reference** folder in the project pane to create a model in that location. In the example below, a common model will be created in the **Models** folder since it's selected.
>
> ![Add model from context menu](https://stoplight.io/api/v1/projects/cHJqOjI/images/AI4lfAIuZPk)

### The Model Editor

The following example shows a data model for user information. This is a common use case for sharing data across APIs.

![Model Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/OEu3MopWsDc)

1. **Model name**: Provide a name for the m
2. **Model description**:  Basic Markdown can be used to format the description text.
3. **Visibility**: Set the model as internal to hide it in public documentation and from guest users. See [API Visibility](../4.-documentation/set-internal-docs.md) for details.
4. **JSON Schema Editor**: Use to build a schema object and examples. See [JSON Schema Editor](json-schema-editor.md) for details.
5. **X-Extensions**: Add extensions to your model.

## Add a Schema in a Request or Response Body

Use this method when the data is unique to a specific response or request. You can't share request or response schemas using this method, but you can use models that are shared with the API, as shown in the following example.

![Schema Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/xmmq7FFDqZs)

To add a schema to a request or response body:

1. Edit an API project.
2. From the **APIs** tab, select an endpoint.
3. Select **+ Add Body** or **+ Response**.
4. Select the content type for your schema. The default is `application/json`.
5. Use the [JSON Schema Editor](json-schema-editor.md) to build a schema object and examples.

> To create request bodies and responses that can be shared across an API, see [Shared Components](shared-components.md).