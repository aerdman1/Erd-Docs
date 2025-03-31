---
title: Project C - Cavatica
deprecated: false
hidden: false
metadata:
  robots: index
---
<PageTemplate project="projectB" />

# $productName$

## $featureName$

Data analyses are project-specific on the Seven Bridges Platform. Before you can start your analysis, you need to create a project.

1. Click **Projects** in the top navigation bar and select **Create a project**.

![694](https://files.readme.io/53fc958-create-a-project.png "create-a-project.png")

2. Name your project.

> 👍 Project URL
>
> Your project will be assigned a [**short name**](https://docs.cavatica.org/docs/the-api#section-project-short-names) based on the name that you give it. While you may re-name your project from the project [**Settings**](https://docs.cavatica.org/docs/modify-project-settings), you cannot change the short name after your project is created.
>
> The **short name** is used as an ID to refer to the project when you access the Platform via the API. It also appears in the URL for the project when you access the Platform via the visual interface.

3. Set general information
   1. Set the **[billing group](https://docs.cavatica.org/docs/manage-billing-groups)** .
   2. Select the [project location](https://docs.cavatica.org/docs/project-and-file-locations). The default location is AWS region **us-east-1**.
   3. (Optional) Change your [spot instance](https://docs.cavatica.org/docs/about-spot-instances) preference. The default setting is **On**.
   4. (Optional) Enable [Reuse (Memoization)](https://docs.cavatica.org/docs/about-memoization).
4. Manage advanced settings
   1. **Network access** - see [Manage Network Access Control](https://docs.cavatica.org/docs/manage-network-access-control)
   2. **File download restriction** - see [Set file download restriction](https://docs.cavatica.org/docs/define-download-restriction)

![590](https://files.readme.io/b7ecef3-create-a-project.png "create-a-project-2.png")

5. Click **Create**, and your new project will be created.

> 📘 Change the Project URL
>
> Note that before you click **Create**, you can edit your project's URL and its **[short name](https://docs.cavatica.org/docs/the-api#section-project-short-names)**.