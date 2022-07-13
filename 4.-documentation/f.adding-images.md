# Add Images

There are two ways to add images to a project:

- **Drag-and-drop (recommended for Web projects)**: Drag-and-drop an image file from your local computer directly into a Markdown file. The image will be stored in Stoplight and respect [project permissions](../2.-workspaces/l.project-roles.md). You must have **Editor** permissions or higher to drag-and-drop images onto Markdown files. This is supported for both Web and Git projects.
- **Import File/Add Image (recommended for Git projects)**: Select the **Add** (+) icon at the top of the left panel, and then select **Import File** or **Image**. Use this method if tracking changes to images is important to you or if the image is shared with another publishing tool. This is only supported for Git projects.

You can add multiple images to any documentation file. Supported image formats include: **JPEG,** **JPG**, **PNG**, and **GIF**.

## Drag-and-drop Images

1. Edit a project, and then open a Markdown file in code view.
2. Drag and drop an image onto the page.
3. Preview the image.

![Add an Image](../assets/images/image-upload.gif)

## Import Images

<!-- theme: warning -->
> **Warning**: This option is only available for public Git repositories. Use the drag-and-drop method for adding images to projects that aren't connected to public Git repositories.

1. Edit a project.
2. Select the **Add** (+) icon at the top of the left panel, and then select **Import File** or **Image**.
3. Navigate to and select the image file you want to import. An `assets/images` folder is added to your **Files** tab if the folder doesn't already exist, and the image is imported into this new folder.
4. Reference the image in a Markdown file using the format `![Image alt text](./path/to/image)`. For easy linking, right-click on an image in the `assets/images` folder, and then select **Copy Relative Path**.
    - For example: `![Image Example](assets/images/style-guides-paths-target.png)`

## Customize Images

To customize images, such as adding backgrounds, captions or focus, check out [images in Stoplight Flavored Markdown](stoplight-flavored-markdown.md).

## Next Steps

With your documentation ready, let users experience it by sharing it. For external users, share your URL. For internal or private projects, [invite users](../2.-workspaces/d.inviting-your-team.md) to the workspace directly.