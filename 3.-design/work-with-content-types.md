# Work with Media Types

<!-- markdown-link-check-disable-next-line -->
[Media types](https://spec.openapis.org/oas/v3.1.0#media-types) declare the format of request or response body content. 

For example: 
- An endpoint on the server allows accepting PDF files with `application/pdf` for a file upload.
- An endpoint may return a PNG image with `image/png` for display on a web page.
- A client and server may exchange messages with `application/json` or `application/xml`.

The Studio Form Designer provides a set of media types that you can easily add to request and response bodies. REST APIs designed with Open API often use `application/json` for communicating messages in the request and response bodies, but you are not required to do so.

![media-type.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/mrrzkTS703E)

If a media type you need is not listed, you can manually add it to the list.

Within a single operation, you can add multiple media types to request and response bodies as needed. Each media type indicates the supported content in body. The following example shows a request body with three media types: `application/json`, `application/pdf`, and `text/html`. This indicates that the operation accepts either a JSON document, a PDF file or a HTML document in a single request.

![Mutliple Media Types](https://stoplight.io/api/v1/projects/cHJqOjI/images/aYpG8hvuopc)

Here is a snippet of an Open API spec in JSON for this example:
      
```json
       "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {}
              }
            },
            "application/pdf": {
              "schema": {
                "type": "object",
                "properties": {}
              }
            },
            "text/html": {
              "schema": {
                "type": "object",
                "properties": {}
              }
            }
          }
        }
      }
```     

## Work with Multipart and Form Requests

You can use the `multipart/form-data` media type to include files with other data. 

For example, the following steps explain how to use the `multipart/form-data` media type to upload files for POST, PUT, and PATCH operations. 

In the Studio Form Editor:

1. Edit an API project, and then select the **APIs** tab.
2. Select a POST, PUT, or PATCH operation, or add a new one.
3. Select the **Add Body** button, and then select the **multipart/form-data** media type.

![Add Body - Multipart/form-data](https://stoplight.io/api/v1/projects/cHJqOjI/images/0rJBrIE11dM)

4. In the **Schema** section, select the **plus** symbol next to **object**, and then add a string object, such as **file:string**.
5. Select the **Object Properties** icon for the string object, and then select **binary** as the format.
![Multipart Properties](https://stoplight.io/api/v1/projects/cHJqOjI/images/T8D9x2qCnwY)

### View JSON

Select the **Code** button to view the JSON for the operation.

```json

   "requestBody": {
          "content": {
            "multipart/form-data": {
              "schema": {
                "type": "object",
                "properties": {
                  "file": {
                    "type": "string",
                    "format": "binary"
                  }
                }
              }
            }
```

### Try It and Mocking
In Edit mode: Select **Preview**, and then select **Try It**. You can then select **Upload** to navigate to a file. 

![Try It](https://stoplight.io/api/v1/projects/cHJqOjI/images/HqRH9m8wLmY)

From published documentation, you can send a request to a live server or a mock server. Mock servers currently do not support requests for `multipart/*`media types, however.  











