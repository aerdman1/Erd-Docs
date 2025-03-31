---
title: Project B - Cancer Genomics
deprecated: false
hidden: false
metadata:
  robots: index
---
<PageTemplate project="projectB" />

# $productName$

## $featureName$

Before you can start analyzing your data, you need to create a project. There are two types of projects on the CGC, **Open** and **Controlled Data Projects**.

> 📘 Protecting Controlled Data
>
> [Controlled Data Projects](https://docs.cancergenomicscloud.org/docs/projects-on-the-cgc) protect Controlled Data by restricting access to users with dbGaP access permissions to TCGA Controlled Data and TARGET Controlled Data.

To create a project:

1. Click the **Projects** tab on the top navigation bar and select **Create a project** from the drop-down menu.

![Screenshot]($image1Url$)

Create a project

> 👍 Unique project URL
>
> Your project will be assigned a [**short name**](https://docs.cancergenomicscloud.org/docs/the-cgc-api#section-project-short-names) based on the name that you give it. While you may re-name your project from the project [**Settings**](https://docs.cancergenomicscloud.org/docs/modify-project-settings), you cannot change **short name** after your project is created. The **short name** is used as an ID to refer to the project when using the API, and also appears in the URL for the project, which is used to access it in your web browser.

2. Name your project.
3. Define the project type if you have Controlled Data access. If you don't have Controlled Data access, all your projects are Open Data Projects by default.
4. Set general information:
   1. Set the [billing group](https://docs.cancergenomicscloud.org/docs/manage-billing-groups) .
   2. Select the [project location](https://docs.cancergenomicscloud.org/docs/project-and-file-locations). The default location is AWS region **us-east-1**.
   3. (Optional) Change your [spot instance](https://docs.cancergenomicscloud.org/docs/about-spot-instances) preference. The default setting is **On**.
   4. (Optional) Enable [Reuse (Memoization)](https://docs.cancergenomicscloud.org/docs/about-memoization).
5. Manage advanced settings:
   1. **Network access** - see [Manage Network Access Control](https://docs.cancergenomicscloud.org/docs/modify-project-settings#manage-network-access-control)v
   2. **File download restriction** - see [Set file download restriction](https://docs.cancergenomicscloud.org/docs/define-download-restriction).
6. Click **Create** to finish creating the project.

> 📘 Computation and Storage Credits
>
> Your CGC account comes with [Amazon Web Services (AWS)](https://aws.amazon.com/) computation and storage credits. You should be able to run your first analysis without adding additional funding.

> 📘 Change the Project URL
>
> Note that before you click **Create**, you can edit your project's URL and, by association, its **[short name](https://docs.cancergenomicscloud.org/docs/the-cgc-api#section-project-short-names)**.