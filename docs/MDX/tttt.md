---
title: tttt
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
Workspaces provide custom, use-case-driven views of the Axonius platform. They act as tailored "skins", allowing different users to easily navigate the product and quickly realize value for specific objectives. Upon login, users are presented with a focused interface relevant to their role or the problem they are trying to solve.

Each workspace features a left navigation bar with the assets and functions most relevant to that specific use case.

![ExposureManagementWorkspace.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/ExposureManagementWorkspace.png)

Each workspace includes:
* A Home page that is the default landing page for each workspace (except for the Axonius Platform). The Home page displays a dashboard that gives immediate insights on your data, including KPIs and insights on common use cases in the context of the workspace. Each workspace had a default Home page dashboard that is managed by Axonius and cannot be edited or deleted. Admin users can set a different dashboard as the workspace Home page. 
* A focused navigation menu that highlights relevant assets and modules to help users focus only on the workspace use cases. While a workspace is a focused environment, all Axonius modules and functionality are available from the More menu at the bottom the the navigation menu.
* A focused asset view on the assets page shows the assets most relevant to the workspace use case.
* Default custom table views of specific assets in some workspaces.

See [Getting to Know the Axonius Interface](/pl/docs/getting-to-know-the-axonius-interface) to learn about the tools available in the top pane of each workspace.

Each workspace has its own use-case-focused navigation menu on the left. The main assets and tools related to the workspace each have an icon and you can navigate directly to those asset pages. 

![LeftNavCutout-MoreMenu.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/LeftNavCutout-MoreMenu.png)

Once displayed, you may need to scroll to see all the options.

**System Permissions for Workspaces**
Admins with the **Manage Workspaces** permission can change the dashboard for the workspace **Home** page.

<HTMLBlock>{`
<div style="background:yellow;padding:10px;text-align:center;">
(Internal)
Links to each available workspaces

## Available Workspaces
The following workspaces are available: 
    ::: info (Note:)
    The available workspaces are dependent upon the modules to which you have access.
</div>
`}</HTMLBlock>

* [**Axonius Platform**](/pl/docs/main-workspace) - The **Axonius platform** leverages an expansive integration network, and automation capabilities to give security and IT teams a unified asset data model that enables proactive security measures at scale. With comprehensive visibility and actionability in a unified view, Axonius helps organizations simplify and take action through automated response and remediation.

* [**Agent Coverage**]() - Axonius Agent Coverage Hub gives your organization complete visibility into your agent coverage and security posture. Out-of-the-box it allows you to quickly act on meaningful insights related to deployment of endpoint security tools, including: vulnerability assessment tools, networking tools, backup agents, and more.
* [**SaaS Applications**](/pl/docs/saas-management-workspace) - Axonius SaaS Applications provides full visibility across your entire SaaS landscape to build a complete inventory, mitigate critical risk areas, and optimize usage and spend. It ensures that every application, managed or unmanaged, is discovered and fully optimized for risk, performance, and cost.

* [**Exposures Management**](/pl/docs/vulnerability-management-workspace) - Axonius Exposures provides a comprehensive approach to managing and mitigating risk across your entire IT ecosystem. Exposures aggregates data from various sources and continuously discovers assets, helping you stay on top of your environment in real time.
* **Exposures: Operations** - Exposure Management offers a holistic view to track, assess, and mitigate risks across your entire IT ecosystem, ensuring comprehensive risk oversight.
* [**Identity Management**](/pl/docs/identities-workspace) - Axonius Identity Management transforms fragmented identity data into actionable insights bringing core discovery, lifecycle, governance, and posture management together in one place to strengthen your IAM program resilience. It provides tools to optimize identity operations by unifying data from all downstream systems and applications.
* [**Software Management**](/pl/docs/software-management-workspace) - Axonius Software Management eliminates manual, outdated assessments by automatically inventorying software across all devices. With a unified view and deep context (user ownership, vulnerabilities, approval status, version EOL, license control) teams can optimize security, reduce risk, and streamline IT operations.
* **SaaS Inventory Discovery** - Gain full visibility into your organization's SaaS inventory. This workspace helps you identify managed versus unmanaged applications, onboard or block Shadow SaaS, and manage SaaS-to-SaaS extensions and shadow extensions to ensure comprehensive oversight of all SaaS assets.
* **SaaS Posture Management** - Axonius SaaS Posture Management helps you identify and remediate security misconfigurations across your SaaS applications. This ensures you can enforce robust security policies and maintain continuous compliance with industry standards.

:::

## Accessing a Workspace
You access workspaces from the Workspaces list.

**To select a workspace:**
1. At the top of the left navigation bar, click **Workspaces** and select a workspace.
![WorkspaceSelector.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/WorkspaceSelector.png)

2. From the workspace selection box, select the workspace you want to work with.
![WorkspaceSelectorBox.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/WorkspaceSelectorBox.png)

3. The left navigation bar and Home page dashboard of the selected workspace are displayed. The name of the workspace appears next to the Axonius logo.

**To access a workspace:**
1. Above the left navigation menu, click **Workspaces** (or the name of the currently selected workspace).
![IdentitiesWorkspaceSelector.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IdentitiesWorkspaceSelector.png)

2. In the workspace selection box, choose the workspace you want and click **Select**.
![WorkspaceSelectionBoxIdentities.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/WorkspaceSelectionBoxIdentities.png)

3. The [Identities Home page](/pl/docs/identities-home-page) is displayed. The name "Identities" appears next to the Axonius logo.
![Identities-Homepage.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Identities-Homepage.png)

## Changing the Workspace Home Page
Each workspace has a Home page that displays a default dashboard with use-case relevant charts. These dashboards are managed by Axonius and cannot be edited or deleted. However, Admin users can select another dashboard as the Home page dashboard provided that dashboard has "Shared" access privileges. Shared dashboards are listed under the "Shared" folder of the Dashboards page.

<Callout icon="📘" theme="info">
Note:

When changing a dashboard to Shared access, all queries used by the charts in the dashboard are also changed to Shared access and will be available to all users with the selected roles across all data scopes.
</Callout>

**To set a dashboard to Shared:**

1. Go to the Dashboard page and, in the folders pane, locate the dashboard you want to use as a Home page. Alternatively, go to the Dashboard Manager page and locate the dashboard you want.
2. From the 3-dot more menu, select Edit.
![ChangeDashboardPermissionsEdit.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/ChangeDashboardPermissionsEdit.png)

3. Select **Share with selected roles within all Data Scopes**. Note that the folder selected in the "Folder" section is changed to "Shared".
![ChangeDashboardPermissionsbox.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/ChangeDashboardPermissionsbox.png)

4. Click **Save**.

**To change the Home page dashboard:**
1. Go to the Dashboard Manager page and locate the dashboard you want.
2. Select a dashboard and from the 3-dot more menu, select Set as Homepage for and then select a workspace.
3. The dashboard is set as the workspace Home page.
![HomePageDashboardSelect.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/HomePageDashboardSelect.png)

    When a workspace is disabled in the list, the selected dashboard is already set as the Home page of that workspace.
