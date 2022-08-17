---
stoplight-id: zumkfdc16oypw
---

# JSON Schema Editor

The JSON Schema Editor helps you design and model data structures used by your API. 

Use the JSON Schema Editor to create:

- API request and response bodies for an API endpoint
- Data models that can be used across one or more APIs

## Form Editor vs. JSON Generator

There are two ways to create schemas:

- Use the [**Form Editor**](#use-the-schema-form-editor) to create data structures in an easy-to-use, graphical format.
- Use the [**Generate from JSON**](#generate-the-schema-from-json) option to create the data structure with raw JSON.

While each method can be used individually, you'll likely find yourself using a combination of both methods while [creating schemas and models](models.md). 

Here's a simple example of a schema for a model in the **Form Editor**. The schema contains a single object with:

* `feature-name`: A string field that's required
* `feature-flag`: A boolean field that has `false` set as the default value

![JSON Schema Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/X7HkjaIThi4)


Depending on the format of your API, JSON or YAML are automatically generated from what you configure in the **Form Editor**. Here's the generated JSON in the **Code** view for the same example:

```json lineNumbers
{
  "content": {
       "application/json": {
         "schema": {
           "type": "object",
           "properties": {
             "feature name": {
               "type": "string",
             },
             "feature on or off?": {
               "type": "boolean",
               "default": false
             }
           },
           "required": [
             "feature name"
           ]
         }
      }
   }
}   
```

Depending on your comfort and skill level, you may find it easier to use one approach over the other.

## Use the Schema Form Editor

![Use the JSON Schema Editor for a model](https://stoplight.io/api/v1/projects/cHJqOjI/images/zRuHbNnzo2M)


1. Open a model, request body, or reponse body, and then navigate to the **Schema Editor**. See [Models and Schemas](models.md).
2. Use the tabs to switch between schemas, examples, and x-extensions (models only).
3. [Add fields](#add-fields-to-the-object) to the schema object.
4. Add [$refs/shared components](shared-components.md) to the object. Select the down arrow to see a read-only view of the referenced object. Select the icon to open an editable view of the referenced object.
5. [Set properties](#set-field-properties) for each field.

### Add Fields to the Object

Field names can be composed of any alphanumeric characters, but names must be unique on the same level. You can reuse field names on nested objects, however.
  
To add fields to the schema object:

1. Select the **+** (plus) icon next to the root **object**. 
2. Select the **name** label to add the **field name** (or **key**). 
3. Select the **string** label to the right of the field name to set the field **type**. 
4. Press **Enter** to quickly add another field.

<!--
focus: false
-->
![Type Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/EbvqhLdTtIs)

The default type for new fields is `string`. Other types include:

  - objects (for nesting objects)
  - array
  - number
  - integer
  - boolean
  - null
  - [reference](shared-components.md#shared-models) (a.k.a. `$ref`)

Field types can also include combination types that allow for object inheritance from other data structures and models:

  - allOf 
  - oneOf 
  - anyOf 

### Organize Fields

You can move, copy, and delete fields that aren't at the root level. At the root level, you can open the **Type Editor**, and then change the type.

Hover over a field to:

* **Move fields**: Use the up and down arrows to organize fields in an object.
* **Copy fields**: Select the **Duplicate** icon to copy a field. 
* **Delete fields**: Select the **Delete** icon.

![JSON Schema Editor Field Actions](https://stoplight.io/api/v1/projects/cHJqOjI/images/UNAlAeYzQkY)

### Set Field Properties

Optionally, you can set properties and extra validations for each field. In the **Form Editor**, properties adhere to the [JSON Schema vocabulary](https://json-schema.org/), making this an easy way to customize fields without referring to the spec.

For example:

- **Enumerations** (or _enums_ for short) allow you to restrict the contents of the field to be specific values. For example, if you are creating a `color` field of type string, you may want to restrict the strings used in that field to specific colors (red, blue, and green).

![enum Example in a model](https://stoplight.io/api/v1/projects/cHJqOjI/images/B9IwCCMWEPs)

- **Format** allows for describing the format of field (string, number, and integer types). Formats depend on the field type; for type string,  you can choose date, time, IP address, URI, and other formats.

- **Example** enables you to provide sample data for each field. This can be used to automatically [generate examples](#generate-examples) for your schema.

- **Required** ensures that the field is present in all requests.
  
In addition to the validations listed above, there are also per-type validations that can be used depending on the type of the field. For example, string validations include setting a minimum/maximum length and regex pattern. For numbers, you can set minimum/maximum values and validate that the numeric value is a multiple.

## Generate the Schema from JSON

You can add raw JSON directly to the Schema Editor if you are familiar with the format or you have a pre-existing JSON Schema representation of your data structure.

You can then use either the **Form Editor** or the **Code View** to tweak the schema.

To generate the Schema from JSON:

1. Open a model or request or reponse body, then navigate to the **Schema Editor**. See [Models and Schemas](models.md).
2. Select **Generate from JSON**.
3. Write or paste an existing JSON schema into the box. 
4. Select **Generate**. (If the JSON isn't valid, the **Generate** button is disabled.)

![Generate JSON in a model](https://stoplight.io/api/v1/projects/cHJqOjI/images/hV7iJqECV5M)

## Generate Examples

The JSON Schema Editor can automatically create examples based on your data model. Use the generated examples as a starting point that you can modify as needed to provide guidance to your users.

Example data comes from:

- The example property set for each field
- enum values, if the example property isn't set
- default values, if the example property isn't set

To create schema examples:

1. On the **Schema** tab, define your data model.
2. Include the **Example** property for each field.
3. Select the **Example** tab, and then select **+ Example**.
4. Modify the example to meet your needs.
5. Select **+ Example** again to add more examples to the schema.

![Example for a model in the JSON Schema Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/V9ebGXGv7g8)


