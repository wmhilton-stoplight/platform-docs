# Add Images

There are two ways to add images to a project:

- **Drag-and-drop**: Drag-and-drop an image file from your local computer directly into a Markdown file. The image will be stored in Stoplight and respect [project permissions](../2.-workspaces/l.project-access.md). You must have **Editor** permissions or higher to drag-and-drop images onto Markdown files.
- **Import File/Add Image**: Select the **Add** (+) icon at the top of the left panel, and then select **Import File** or **Image**. Use this method if tracking changes to images is important to you or if the image is shared with another publishing tool.

You can add multiple images to any documentation file. Supported image formats include: **JPEG,** **JPG**, **PNG**, and **GIF**.

## Drag-and-drop Images

1. Edit a project, and then open a Markdown file in code view.
2. Drag and drop an image onto the page.
3. Preview the image.

![Add an Image](../assets/images/image-upload.gif)

## Import Images

1. Edit a project.
2. Select the **Add** (+) icon at the top of the left panel, and then select **Import File** or **Image**.
3. Navigate to and select the image file you want to import. An `assets/images` folder is added to your **Files** tab if the folder doesn't already exist, and the image is imported into this new folder.
4. Reference the image in a Markdown file using the format `![Image alt text](./path/to/image)`. For easy linking, right-click on an image in the `assets/images` folder, and then select **Copy Relative Path**.
    - For example: `![Image Example](assets/images/style-guides-paths-target.png)`

## Customize Images

To customize images, such as adding backgrounds, captions or focus, check out [images in Stoplight Flavored Markdown](stoplight-flavored-markdown.md).

## Image Visibility

Images that are uploaded to Stoplight via the drag-and-drop method will have a image URL such as: https://stoplight.io/api/v1/projects/cHJqOjI/images/f411rdRcvGA.

The image URL has the same visibility as the Stoplight project visibility, so images uploaded to a public project will be visible by anyone who has access to the image URL, while images uploaded to internal or private projects will only be visible by users who have access to those projects in Stoplight.

For private Git repositories that are connected to a public Stoplight project, Stoplight will display a public copy of any images in the repository that are included in a Markdown article or API documentation. That way users can view a project's documentation as it was intended without having access to a Stoplight project, and Stoplight users can still use a private Git repository.

## Limitations

Stoplight supports uploading images with a file size of up to 15 MB.

If you have an image in a Git repository that's larger than 15 MB, that image won't be displayed in your Stoplight project.

## Next Steps

With your documentation ready, let users experience it by sharing it. For external users, share your URL. For internal or private projects, [invite users](../2.-workspaces/d.workspace-access.md) to the workspace directly.