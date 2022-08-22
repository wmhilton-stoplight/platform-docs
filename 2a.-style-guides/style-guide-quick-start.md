# Style Guide Quickstart

Follow these steps to use style guides that bring consistency and easy governance to your API program.

Use one of these approaches:

* Create a style guide that you can share across all API projects in your workspace (Professional plan and above). See [Create a Shareable Style Guide](#create-a-shareable-style-guide).
* Create rules in an API project. These rules can't be shared. See [Use a Local Style Guide](#use-a-local-style-guide).
* Enable public style guides in your projects, then customize rules to meet your organizations needs. See [Reuse and Customize Rules](reuse-and-customize-rules.md).

## Create a Shareable Style Guide

### 1. Create a Style Guide Project

1. Log in to your workspace, and then select the **Add** icon (+) at the top of the left pane.
2. From the **Create or Import a Project** page, select the **Style Guide** tab.
3. Provide a name for your style guide, and then select **Create Style Guide**.

![Quickstart Create Style Guide ](https://stoplight.io/api/v1/projects/cHJqOjI/images/WxHMDvz4miI)

### 2. Review Stoplight Rules

All projects contain a default set of rules and targets for the OAS (OpenAPI Specification).

Rules and targets are organized under the **Inherited** list in the left navigation panel. 

1. Select an inherited rule.
2. Review the rule's documentation. 
3. Review the rule's properties.

![Sample Rule](https://stoplight.io/api/v1/projects/cHJqOjI/images/I2UDPwPEW88)

> If you don't want your API validated against a specific rule, select **Disabled** from the **Severity** list in the Rule Editor. ![Disable a rule](../assets/images/style-guide-disable-rule.png)
>You can also [disable the entire default style guide](d-enable-style-guide.md#disable-a-style-guide).

### 3. Create a Local Rule

1. Select the **Add** icon (+), and then select **Add Rule**.

![Add rule icon](https://stoplight.io/api/v1/projects/cHJqOjI/images/5JDWYZgLJx8)

2. Configure the three main rule areas:
    * [Rule Settings](c-create-rules.md#Rule-Settings)
    * [Given Settings](c-create-rules.md#Given-Settings)
    * [Then Settings](c-create-rules.md#Then-Settings)

See [these examples](g-rule-examples.md) to get started.

### 4. Publish the Style Guide

Select **Publish** to make your style guide available to API projects in your workspace.

> If your style guide contains [validation errors](k-validate-style-guides.md), the **Publish** button is disabled.

### 5. Enable the Style Guide

The APIs in your project are validated against the style guides you enable.

1. Edit an API project.
2. Select the **Styles** tab in the left pane.
3. On the Overview pane, select **Manage Style Guides** from the **Enabled Style Guides** page.
4. In the **Style Guides** dialog box, select **Enable** for one or more style guides.
5. Select **Save**.

## Use a Local Style Guide

1. Log in to your workspace, and then edit an API project.
2. Select the **Styles** tab.

![Styles Tab](https://stoplight.io/api/v1/projects/cHJqOjI/images/AXPMWsBbv8o)

3. Review the [Stoplight rules](#review-stoplight-rules).

### Validate Your API

1. Select the **APIs** tab.
2. Notice that your API is automatically validated against the Stoplight rules.

![API Designer Checker Feedback](https://stoplight.io/api/v1/projects/cHJqOjI/images/n1wKmilw5uk)

3. Select each entry in the list to go directly to the **Code** view for that problem.

### Manage Styles

From an API project, you can:

* [Create rules](#create-a-local-rule) specific to the API project. Note that these can't be shared.
* [Disable rules](j-disable-rules.md) in the Stoplight Style Guide. 
* [Disable the Stoplight Style Guide](d-enable-style-guide.md#disable-a-style-guide).