# Shared Components

When using Stoplight, or OpenAPI in general, there are various different
components that can be either defined within an endpoint or reused between multiple endpoints. To help reduce repetition (and the chance of introducing errors), it's important to:
* Identify endpoints with common parameters, schemas, request bodies, or responses.
* Use shared components to reference the same component multiple times instead  of rewriting the properties for each individual endpoint.

Shared components in Stoplight come in several forms:

* **[Models](#shared-models)**: Also known as schemas, these are the most common shared component. They describe the actual shape of the data for JSON requests and responses.

* **[Request Bodies](#shared-request-bodies)**: Content and content types, along with a schema for each type, examples, and a description. 

* **[Responses](#shared-reponses)**: Common responses like page not found, validation errors, etc. 

* **[Parameters](#shared-parameters)**: Parts of the request: query string parameters, path parameters, headers, and cookies. 

* **[Examples](#shared-examples)**: Show how a request or response body might look. These can be generated from schemas automatically, but can also be manually created for more complex scenarios.

Most shared components can be used within a single API file. Models can be used within an API file, within a project, and across Stoplight projects (with design libraries, which are in a closed beta release).

| Shared Component | Within an API | Within a Project | Across Projects* 
|---------|----------|---------|---------|
| Models   | ✅ | ✅ | ✅ |
| Request Bodies | ✅ |  |
| Responses |✅ |  | 
| Parameters | ✅ |  |
| Examples | ✅ |  | 

\* With design libraries enabled. Design libraries are in a closed beta release. 

## Shared Models

While designing your APIs, you will often find yourself repeating structures in your endpoint request and response bodies. For example, you might have an API endpoint that returns a list of users, and another endpoint that returns a single user. The response structures of these two endpoints will be similar: one is responding with an array of user objects, and one is responding with a single user object.

Models allow you to describe these common structures (for example, a User object), and then reference the object from endpoint definitions, or even from other models. Then, future updates are made in one place instead of many places.

Splitting your API descriptions across multiple files using $ref (references) allows for cleaner and more organized code. 

Use shared models to:

- De-duplicate common structures like models, reducing repetition and allowing them to be used for other purposes like [contract testing](https://apisyouwonthate.com/blog/writing-documentation-via-contract-testing).
- Similar parameters or headers can be shared across multiple endpoints.
- Examples for request or response bodies can be reused.

See [Models and Schemas](models.md) to learn how to create a model.

### Use Shared Models

1. Select an **endpoint** or **model**.
2. Create a **request body** and/or **response body**.
3. Within the JSON Schema Viewer, add a new property or modify an existing property.
4. Select **\$ref**.
5. Select a **\$ref target** and model:
    * **External URL**: Use a fully qualified URL to reference an external model.
    * **This File**: Select a model in the current API.
    * **This Project**: Select a model in the current Stoplight project.
    * **Design Library**: Coming soon.

![Shared Models Example](https://stoplight.io/api/v1/projects/cHJqOjI/images/gIUDTdG7DNY)

## Shared Responses

Shared responses allow you to reference a single response multiple times without having to recreate each response manually. The added benefit of this approach is that updates to the shared response object are automatically propagated to any endpoint using that object.

Shared responses allow you to configure the following properties:

* **Headers** - Customize the HTTP Headers returned in the response.
* **Response body** - Customize the HTTP message body contents using the Stoplight modeling tool (or reference a pre-existing model).

### Add Shared Responses

To create a shared response:

1. Select the **APIs** tab.
2. Right-click on the **Responses** folder.
3. Provide a name for the shared response, and then press **Enter**.
4. In the Editor pane, add shared headers or a response body.

### Use Shared Responses

To use a shared response:

1. Navigate to an API endpoint.
2. In the **Response** area of the form, select the shared response from the **No shared response selected** list. 
3. Select the corresponding response code (example: 400).

![use-shared-response.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/oaQyqBxmem8)

Select the **Go to Shared Response** button to open the shared response. Changes you make to the shared response impact all references.

### Shared Response Example

Use shared responses when you have a set of API endpoints that should return the same error response when a failure occurs. When an error is returned from the API, the API uses a custom error format instead of using a standard one like [RFC 7807](https://tools.ietf.org/html/rfc7807):

* `msg` - A descriptive error message about the failure in string format.
* `error_code` - A code representing the category of the failure in integer format.
* `response_id` - A tracking ID that can be used by the caller to follow-up with an administrator for more information.

This examples shows a shared response called BadRequest with `propertiesmsg`, `error_code`, and `response_id`.

![shared-response-properties.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/RieBUdLdjdw)

_This response is part of the <a href="https://meta.stoplight.io/docs/sample-specs/reference/giphy/giphy.yaml">Giphy</a> example in sample-specs._

Create a new shared response, giving it a name like `BadRequest`, `NotFound`, `Forbidden`, etc.

Add the schema, or reference one that already exists, with the properties that will appear in the HTTP body.

Add a short description of the error response, such as what's likely to have triggered it, and where the user can find out more information to resolve it. If documenting an API error, and the error message itself has links and sufficient information to solve the problem, then this can be more brief. You can also add examples.

Now when you update the shared response, it will update in every endpoint using this response.

## Shared Parameters

Describing an HTTP request involves talking about the URL, method, and body. Everything else is a parameter. 

  * **path** - Dynamic values in the path part of the URL (example: `/people/{id}`).
  * **query** - Dynamic values in the query string part of the URL (example: `/planets?name=Endor`).
  * **header** - Custom headers that are expected as part of the request.
  * **cookie** - Used to pass a specific cookie value to the API.

Attributes and validations can be added to the parameter values to describe things like data type, default values, examples, restrict to a specific set of values (enum), and even marking parameters as deprecated to signal to API consumers that the parameters should no longer be used.

### Add Shared Parameters

To add a shared parameter:

1. Select the **APIs** tab.
2. Right-click on the **Parameters** folder.
3. Select the type of parameter to create.
4. Provide a name for the parameter, and then press **Enter**.
5. Define parameter properties in the Editor pane.

![Query Parameters](https://stoplight.io/api/v1/projects/cHJqOjI/images/rn0pfNwM34U)

### Use Shared Parameters

To use a shared parameter:

1. Navigate to an API endpoint.
2. Add one of the following:
   * In the **Path Param** section, select the **Plus** icon.
   * In HTTP request information section, select **Header** or **Query Param**. 
3. Select the link icon to choose the parameter to reference.
 
![Shared Parameters](https://stoplight.io/api/v1/projects/cHJqOjI/images/fCddCvk61bY)

Once the parameter has been referenced, any updates to the shared parameter will automatically be propagated to every endpoint using that parameter. Like other references in Stoplight, shared parameters can also be shared across files, projects, and other external sources.

### Shared Parameters Example

For example, you are creating an API to serve thousands of cooking recipes. When dealing with large volumes of data, you typically want to avoid sending _all_ data in a request. To help avoid sending more data than is necessary, most applications implement a "paging" feature that allows clients to retrieve a small portion of result, such as a single page.

There are multiple ways to approach a paging feature. For this example, add two query string parameters to every request:

* `limit` - The number of results to return when viewing a page. For example,  setting `limit` to `20` means that, at most, 20 results will be returned in the request.
* `offset` - The number of results to skip before returning results. For example, setting an `offset` of `20` means that the API will discard the first 20 results.

By using the two parameters above, a client can efficiently "page" through results, only returning items that are within the requested bounds. To demonstrate, use the parameters to display the first page of recipe results:

```
GET /recipes?limit=20&offset=0
```

Since the `offset` is set to `0`, the API won't discard any results. Paired with a `limit` of `20`, only the first 20 results are shown (1 through 20). 

To view the second page of recipes, use:

```
GET /recipes?limit=20&offset=20
```

By setting an `offset` of `20`, the API will discard the first 20 results. Paired again with a `limit` of `20`, the second page of results is shown (21 through 40).

## Shared Examples

Shared Examples can be applied to a request body or a response body. Defining an example gives you more power over how that model is displayed in mock servers and documentation tools. 

### Add Shared Examples

To add a shared example:

1. Select the **APIs** tab.
2. Right-click on the **Examples** folder, and then select **New Example**.
3. Select the type of parameter to create.
4. Provide a name for the example, and then press **Enter**.
5. Define example properties in the Editor pane.

![Shared Example](https://stoplight.io/api/v1/projects/cHJqOjI/images/a7SsfW5eo4Y)

### Use Shared Examples

To use a shared example:

1. Navigate to an API endpoint.
2. In the **Request** or **Response** area of the form, select the **Example** tab.
3. Select the shared example from the **No shared response selected** list. 

![Use Shared Examples](https://stoplight.io/api/v1/projects/cHJqOjI/images/aSWhQWtiS1U)

Select the **Go to Shared Example** button to open the shared response. Changes you make to the shared response impact all references.