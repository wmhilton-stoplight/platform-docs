---
tags: [Documentation]
---

# Publish Documentation

If the right people can't find your API documentation easily, there's not much use of having a fantastic developer experience. 

**For internal APIs**, you should use the Explorer to allow internal users to find, analyze, and search APIs. Star the important ones to make them easily accessible. Learn how to [invite members of your team](../1.-setting-up-workspaces/d.inviting-your-team.md) to the workspace to give them access to documentation.

**For external APIs**, create a Docs Hub or if a Hub is already published, add projects to it. 

>Multiple Hubs can be created if the goal is to have different views for different users. 

### Create a Docs Hub

A Hub can be used to group a set of your projects, be it documentation or APIs, and publish them for users to discover and consume. 

Get started by creating a new Hub from your workspace.  

<!--screenshot-->

Choose a short name and logo for the Hub. We named ours, `Stoplight Platform`. The path should be prefilled based on the name you chose, but you can choose to edit it if you like. Again, keep it short and straightforward. 

Next up, choose a list of projects you want to add to the Hub. Click **Create**.

<!--screenshot-->

### Configure a Hub

**Configure Projects**

You can configure project settings either while adding a new project or editing it in the *Site Navigation* section. 

- **Choose a particular branch** to show using the branch dropdown. e.g., Release or Master branch
- **Show only a specific part of the project** by choosing a content directory. e.g., Show a project with docs and APIs separately as API reference and Getting Started without changing the project structure, which gives the flexibility to create the navigation according to your needs. 
- **Reorder the Projects** in the preferred order. 

**Add External Links**

- Add external links in the Hub to your blog, status page, and support by clicking the `Add Nav Link button` and choosing `External`.

Once configured, **preview your Hub**. If you're happy with it, **set it live**.

### Set up a Custom Domain

You can set up your custom domain in the *Domain* section. Add the Custom Domain you want to use for your docs, e.g., `https://developer.your-company.io` and click *Save*. 

Next, you will need to set up a CNAME DNS record for your domain in your DNS provider. You can easily set up a CNAME to your site by using the following information:

Type | Name | Value | TTL
---------|----------|---------
 CNAME | `https://your-custom-domain` | ingress.stoplight-local.com |     14400

> The DNS record entry can take up to 8 hours to propagate. 

<!-- To-do ### Organizing your Hub -->