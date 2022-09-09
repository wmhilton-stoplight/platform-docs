---
stoplight-id: x8m99p1dhhvl8
---

# Extensions

Extensions (x-extensions) are used to add capabilities to an API beyond what's provided by a base specification, such as OpenAPI. 

Extensions:

- Are always prefixed with `x-`.
- Don't appear in published documentation.

You can use the **Form Editor** to add extensions to these areas of your API document:

- OpenAPI object
- Operation object
- Schema object (for models)

You can also use the **Code View** to add extensions to any object supported by the base API specification. 

## Stoplight Extensions

### x-internal

Used to hide APIs, operations, and models from public documentation and guest users by marking them as internal. Adding an `x-internal` extension to the root of an API, operation, or model has the same impact as setting the **Internal** flag in the **Form Editor**. See [Set Article and API Visibility](../4.-documentation/set-internal-docs.md) for details.

```json
{
  "x-internal": true
}
```

### x-stoplight

> x-stoplight is reserved for Stoplight use.

Used to indicate the unique identifiers, referred to as stable IDs, to the root of each published API, model, and article. Stable IDs are automatically added to each new, imported, and renamed file in a project. See [Stable ID Guidelines](../4.-documentation/stoplight-urls.md#stable-id-guidelines) for details.

Stable IDs aren't visible in public documentation.

```json
  "x-stoplight": {
    "id": "jknwvq9tvtozp"
  }
```

### OAS 2.x Support

This set of tags is used to extend support for OAS 2.x documents: 

- x-deprecated
- x-example
- x-examples (also supported in OAS 3.x documents)
- x-nullable

### Migration Support

The x-logo extension is used to ensure smooth transition to Stoplight from other tools.