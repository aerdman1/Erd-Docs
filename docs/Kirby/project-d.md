---
title: 'Project D - BioData Catalyst '
deprecated: false
hidden: false
metadata:
  robots: index
---
<PageTemplate project="projectD" />

# $productName$

## $featureName$

Before you can start analyzing your data, you need to create a project. There are two types of projects on the Platform, **Open** and **Controlled Data Projects**.

[Controlled Data Projects](https://sb-biodatacatalyst.readme.io/docs/projects-on-the-platform#controlled-data-projects) protect Controlled Data by restricting access to users with dbGaP access permissions to Controlled Data.

To create a project:

1. Click the **Projects** tab on the top navigation bar and select **Create a project** from the drop-down menu.

![Screenshot]($image1Url$)

Create a project

2. Name your project. Your project will be assigned a short name based on the name that you give it, which is used as an ID to refer to the project when using the API.

![Screenshot]($image2Url$)

3. Define the project type if you have Controlled Data access. If you don't have Controlled Data access, all your projects are Open Data Projects by default.
4. Set general information:
   1. Set the [billing group](https://sb-biodatacatalyst.readme.io/docs/manage-billing-groups) .
   2. Select the [project location](https://sb-biodatacatalyst.readme.io/docs/project-and-file-locations). The default location is AWS region **us-east-1**.
   3. (Optional) Change your [spot instance](https://sb-biodatacatalyst.readme.io/docs/about-spot-instances) preference. The default setting is **On**.
   4. (Optional) Enable [Reuse (Memoization)](https://sb-biodatacatalyst.readme.io/docs/about-memoization).
5. Manage advanced settings:
   1. **Network access** - see [Manage Network Access Control](https://sb-biodatacatalyst.readme.io/docs/modify-project-settings#manage-network-access-control).
   2. **File download restriction** - see [Set file download restriction](https://sb-biodatacatalyst.readme.io/docs/define-download-restriction).
6. Click **Create** to finish creating the project.