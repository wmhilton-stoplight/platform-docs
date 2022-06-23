# Add Images

Visual help on your documentation compliments the text on it and helps users quickly reach their goals. Add flowcharts, graphics, or screenshots to **Getting Started guides** and **Authentication guides** to help better explain flows and use cases. 

There are two ways to add images to a project:

- **Drag-and-drop**: This is the easiest and preferred method of adding images, which are stored in Stoplight and respect project permissions (private vs. internal). You must have Editor permissions or higher to drag-and-drop images onto Markdown files.
- **Import**: For projects connected to Git or another version control system, import files. Use this method if tracking changes to images is important to you or if the image is shared with another publishing tool.

You can add multiple images to any documentation file. Supported  image formats include: **JPEG,** **JPG**, **PNG**, and **GIF**.

## Drag-and-drop Images

1. Edit a project, and then open a Markdown file in code view.
2. Drag and drop an image onto the page.
3. Preview the image.

![Add an Image](../assets/images/image-upload.gif)

## Import Images

<!-- theme: warning -->
> **Warning**: This option is only available for public Git repositories. Use the drag-and-drop method for adding images to projects that aren't connected to public Git repositories.

1. Edit a project.
2. Select the **Add** icon at the top of the left panel, and then select **Import File**.
3. Navigate to and import an image file. If they don't already exist, an `assets\images` directory is added to your **Files** tab, and the image is imported into that.
4. Reference the image in a Markdown file. (For easy linking, right-click on an image in the assets/images tab, and then select **Copy Relative Path**.)

    `![Image Example](assets/images/style-guides-paths-target.png)`

## Customize Images

To customize images, such as adding backgrounds, captions or focus, check out [images in Stoplight Flavored Markdown](stoplight-flavored-markdown.md).

## What's Next?

With your documentation ready, let users experience it by sharing it. For external users, share your URL. For internal or private projects, [invite users](../2.-workspaces/d.inviting-your-team.md) to the workspace directly.