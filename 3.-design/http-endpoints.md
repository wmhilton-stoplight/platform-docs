---
tags: []
---

# Work with Models

Stoplight's Schema Editor allows you to design and model data structures used by your API. The Schema Editor is useful for:

- Drafting API request and response bodies under an API endpoint
- Creating models for your API

There are two different methods for generating a CRUD model:

- Use the JSON Schema **Form Editor** to create data structures
  in an easy-to-use, graphical format.

- Use the **Code Editor** to modify the data structure with raw JSON Schema.

While each method can be used individually, you will most likely find yourself
using a combination of both methods while drafting API endpoints, models, and
responses.

## Use the Editor

<!--
focus: false
-->
![JSON Schema Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/IxIr8mPMdls)

The JSON Schema editor makes data structure creation as simple as
possible. You can find the JSON Schema editor within any model or endpoint while **Form View** is selected.

To use the editor:

- Select **+ Add Body** or **+ Response** within a model or endpoint

- Select the **+** (plus) icon next to the root **object** to add fields
  to the data structure. The plus icon can also be used on nested objects to
  create a hierarchy of arbitrarily nested data structures

- Set the **field name** (or **key**) of a data field by selecting the text label
  to the left of the newly created field. Field names can be composed of any
  alphanumeric characters, but must be unique on the same level. You will receive an
  error if you try to reuse field names multiple times on the same level
  (though they can be reused on nested objects)

- Set the **type** of a field by selecting the **string** label to the right of
  the field name. The default type for a newly created field is 'string',
  however other types include:

  - objects (for nesting objects)
  - array
  - number
  - integer
  - boolean
  - null
  - [reference](shared-components.md#shared-models) (a.k.a. `$ref`)

- Field types can also include combination types:

  - allOf 
  - oneOf 
  - anyOf 
  
These special types allow for object inheritance from other data structures and models.

- Optionally, you can set extra validations on the field. For example:

  - **Enumerations** (or _enums_ for short) allow you to restrict the contents of the field to be specific values. For example, if you are creating a 'color' field of type string, you may want to restrict the strings used in that field to specific colors (red, blue, and green)

  - **Format** allows for describing the specific format of a field, such as date, time, IP address, URI, and email
  
    In addition to the validations listed above, there are also per-type validations that can be used depending on the type of the field. For example, string validations include setting a minimum/maximum length and regex pattern. For numbers, you can set minimum/maximum values and even validate that the numeric value is a multiple.

- Optionally, you can specify a field as **required**, which ensures that the
  field is present in all requests and an error is thrown otherwise.

## Editing the Raw JSON Schema

![Write View](https://stoplight.io/api/v1/projects/cHJqOjI/images/KYtMAa2E1zM)

You can edit the raw JSON Schema directly if you are familiar with the format or have a pre-existing JSON Schema representation of your data structure.

To edit the raw JSON Schema, select the **Code** tab next to the **Form**
tab.

## Try it Out

When modeling endpoints, you can use [the built-in HTTP client](try-it.md) to hit either a real API (a development server, production, for example) or a [mock server](setting-up-a-mock-server.md).
