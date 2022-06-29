# Import Postman Collection

Stoplight enables users to import a [Postman Collection](https://learning.postman.com/docs/sending-requests/intro-to-collections/) file from their local computer directly into Stoplight Studio.

Stoplight converts the Postman Collection to an OpenAPI 3.1 file, and then imports all endpoints (paths) into your Stoplight project. This is a great way to create an OpenAPI specification file for existing APIs, improve its documentation, and collaborate with other teams on API design.

For each Postman Collection file you import into a project, a new OpenAPI specification file is created for it. There is currently no way to keep a Postman Collection and a Stoplight API specification in sync. If that's something you're interested in seeing in the product, add a note to the Stoplight [roadmap](https://roadmap.stoplight.io/tabs/7-under-consideration).

Stoplight supports importing Postman Collection v2 and v2.1 files.

## Export a Postman Collection

To export a Postman collection, in the Postman app:

1. Select the **Collections** tab on the left-side menu.
2. Select the three dots icon next to the collection name, then select **Export**.
3. You can select **v2** or **v2.1**; Stoplight supports both formats.
4. Select **Export** to download your collection as a JSON file.

## Import a Postman Collection into Stoplight Studio

To import your JSON file into Stoplight:

1. Open the Stoplight project you would like to import your collection to.
2. Select the **Add** icon (+) at the top of the left pane, and select **API**.
3. Select **Import Postman Collection**, and select your Postman Collection JSON file on your local file system.

![Stoplight New API modal](https://stoplight.io/api/v1/projects/cHJqOjI/images/xMmT5n6KzlM)

And you’re all set! You should now have a new API in your project with all the information from the endpoints in your Postman Collection.

> **Note**: Stoplight will display an error message at the bottom of the screen if there are any issues importing a Postman Collection file. Some common issues include having invalid URLs and JSON in your file, so make sure that your requests are all valid in Postman before exporting your collection.

For next steps:

- To learn more about working in Stoplight Studio and editing your APIs, check out the [API Design Overview](../3.-design/design-overview.md) section.
- To learn more about validating your API and creating rules to help you create an API governance program, check out the [Style Guide Overview](../2a.-style-guides/a.style-guide-projects.md) section.
