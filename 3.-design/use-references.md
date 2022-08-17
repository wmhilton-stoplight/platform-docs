---
tags: []
---

# Use References

Splitting your API descriptions across multiple files using $ref (references) allows for cleaner and more organized code. 

![References](https://stoplight.io/api/v1/projects/cHJqOjI/images/gIUDTdG7DNY)

Some common use cases are as follows:

- De-duplicate common structures like models, reducing repetition and allowing them to be used for other purposes like [contract testing](https://apisyouwonthate.com/blog/writing-documentation-via-contract-testing).
- Similar parameters or headers can be shared across multiple endpoints.
- Examples for request or response bodies can be reused.

To use a reference:

1. Select an **endpoint** or **model**.
2. For endpoints, create or select a **request body** or **response body**.
3. Select the **+** (plus) icon next to the root **object**. 
4. Select the **name** label to add the **field name** (or **key**). 
5. Select the **string** label to the right of the field name, and then  set the field to **$ref**. 
6. Select a **$ref target**.

Once you add the $ref, select the arrow to see a read-only view the referenced object. 

![View @refs](https://stoplight.io/api/v1/projects/cHJqOjI/images/m91P5osvjy4)

For more information, see [Share Components](shared-components.md).
