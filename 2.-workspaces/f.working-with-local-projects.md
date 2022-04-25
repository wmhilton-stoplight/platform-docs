# Publish with the Stoplight CLI

Stoplight CLI is a command-line tool, available as [an NPM module](https://www.npmjs.com/package/@stoplight/cli), that can publish changes to Stoplight and make them visible in Explorer just like any other project. 

Stoplight CLI projects are **not editable** in Studio Web, but the content is available to read and search. You can [edit content in Studio Desktop](#edit-local-files), however, then publish the files to Stoplight using the CLI.

Stoplight CLI can be used to publish:

* [Local projects](#publish-local-projects) that do not use Git.
* Projects from a [continuous integration server](#continous-integration).

> Images referenced in Markdown files are not currently published with the Stoplight CLI. To publish images with local projects, host them on a supported platform and embed them in Markdown files. See [Embeds](../4.-documentation/stoplight-flavored-markdown.md#embeds) for instructions. 
 
## Prerequisites

1. Install [nodeJS](https://nodejs.dev/).
2. Install the [Stoplight CLI](https://www.npmjs.com/package/@stoplight/cli).

Note that nodeJS version 12 or greater is required to run the CLI. You cae verify your version with the command: `node --version`

## Publish Local Projects

Local projects are not editable in Studio Web, but you can use Studio Desktop to edit files, then publish using the Stoplight CLI.

### Create an Empty Project

1. Log in to your workspace, and then select the **Add** icon (+) at the top of the left pane.
2. From **CLI Project** area of the **Create a Project** page, select **Create Blank Project**.
3. Provide a name for your project, and then set the [project visibility](l.project-roles.md). 
4. Optionally, select group to help organize your projects (Professional plan and above).
5. Select **Create CLI Project**. 

An empty project is created. Next, use the Stoplight CLI to push data to the project.

### Push Local Files

Push local files to the project to analyze OpenAPI files, JSON schemas, and Markdown documentation. Relevant data is pushed to Stoplight, and you can view it in Explorer. 

1. Copy the command on the project setup page. 

![CLI Command](../assets/images/cli-command.png)

2. Navigate to the root folder of your local project, and then run the copied command. 

You can add this command to a [Continuous Integration server](g.automating-publishing.md#stoplight-cli) to update the contents whenever something changes.

### Edit Local Files

1. Download [Studio Desktop](https://stoplight.io/studio). 
2. Use the **Open Existing Folder** option on the Studio Desktop start screen to navigate to the local project.
3. Edit files using the form or code editors. Read the [Studio documentation](https://meta.stoplight.io/docs/studio/) for more specifics.
4. Once you are done editing, push the files using the CLI or automate publishing in [continuous integration](g.automating-publishing.md#stoplight-cli).

## Continuous Integration

1. Navigate to `https://{workspace}.stoplight.io/settings/{project}/automation` in your browser to get the CLI command and token.

![cli-push.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/En5VTdCDhGA)

2. On your file system, make sure you are in the root directory of the project.

```bash
cd /home/src/my-project/
```

3. Run the push command, passing in the project token associated with this project. This will send all the API design and documentation related files to Stoplight, and ignore any unrelated files.

```bash
npx @stoplight/cli@5 push --ci-token {project-token} --url https://{workspace-name}.stoplight.io
```
### GitHub Workflow

The [GitHub Workflow](https://github.com/stoplightio/stoplight-cli-workflow) is a quickstart if you use GitHub. The workflow uses the Stoplight CLI to automatically publish content when a push is made to .json , .yaml, .yml, or .md file in at least one of these cases:

* In the default GitHub branch.
* In branches with names that start with design/ 
* A pull request is made in the repository on any branch

See the [GitHub Workflow Syntax documentation](https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions) for guidance.