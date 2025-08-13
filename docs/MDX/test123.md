---
title: test123
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---


From the **Case Management** table, you can view the following information on any Case:

* [**Case Details**](#viewing-case-details)  - This includes tracking the Case progress, and viewing, modifying, or adding to its configuration.
  * [**Case Assets**](#viewing-case-assets)  - The assets on which the Case was opened.


## Viewing Case Details

In the **Case** drawer of a selected Case, the **Case Details** tab enables you to:

* Track the Case progress.
  * View the Case details.
    * Pivot to the assets resulting from the Base query at the time of Case creation.
      * Pivot to the list of resolved assets or unresolved assets.
        * Pivot to the assets resulting from any Additional query.
          * Pivot to the configuration of any Enforcement Set linked to the Case and view its main Enforcement Action.

            **To view Case details**
            1. In the [**Case Management** page](/docs/case-management-page) , click a Case. The Case drawer - **Case Details** tab opens.\
               ![](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/CaseDetailsDrawer.png)
               1. In the **Case progress** section, you can see the progress of the Case, refresh the progress calculation, and pivot to the initial list of Case assets, resolved assets, or unresolved assets. See below [how to track Case progress](#tracking-case-progress) .
                  2. View the Case information that you set when creating or editing the Case, including **Due Date**, **Status**, **Status Update** (**Auto-update status**), **Priority**, **Created On**, **Case Title**, **Description**, **Type**, **Assignee**, **Base Query**, **Additional Queries**, and **Enforcements Links**. An explanation of these fields is provided in [Creating a New Case](/docs/creating-a-new-case) .- The number of days until the **Due Date** is displayed in color next to the date, only if it is coming up in 1-10 days or is Overdue.
                     - For Cases created using the [**Create a new case** enforcement action](https://docs.axonius.com/enforcements/docs/create-case) , the following notification appears under **Base Query**: This case was created on assets from Enforcement Center action with this query \<query name link>. For example:

  

                     ```
                     ```

                     ![CaseECactionBaseQuery](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/CaseECactionBaseQuery.png)

                     3. &#x20;  To see the assets resulting from the base query, under \*\*Base Query\*\*, click the base query. The \*\*Assets\*\* page opens in a new tab. Click the \*\*Queries\*\* tab. The following screen shows an example of \*\*Users\*\* resulting from the \*\*unclear admin status\*\* query. &#x20;
                        !\[B!\[]\(https\://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/BaseQueryResults.png)TMLBlock>\{\`

                        \<div style="background:yellow;padding:10px;text-align:center;">
                        (Internal) (Private notes)
                        Used to open the Assets page - Queries tab. It now opens the Assets page - Assets tab. You can then open the Queries tab.
                        \</div>
                        \`}\</HTMLBlock>

     
                        5. To see the assets resulting from an additional query, under **Additional Queries**, click a query. The **Assets** page opens in a new tab, displaying the assets resulting from the selected query.
                           7. To view the configuration of an Enforcement Set linked to the Case, under **Enforcements Links**, click the Enforcement Set name. The Enforcement Set configuration page opens. Learn more about the [Enforcement Set fields](/docs/create-ec-set) . Note that you can hover over the icon on the Enforcement Set row to view its main Enforcement Action.\
                              !\[E![](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/EnforcementMainAction.png)

### Tracking Case Progress

The top of the **Case** drawer shows the Case progress (also displayed in the Case Management table under the **Case Progress** column).\
The system automatically calculates the Case progress by dividing the number of resolved assets by the number of assets returned from the initial query, and then multiplying that result by 100 to get a percentage. For example, if there are 200 assets returned by a query that is linked to a case and 20 of those assets become resolved, the progress is 20/200 = 0.1 = 10%.

* Progress results are updated automatically each time \[Asset Investigation]\(/docs/advanced-asset-investigation)  is performed or every Discovery Cycle. You can recalculate Case progress at an earlier time, by clicking the Refresh icon !\[RefreshIcon]\(https\://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/RefreshIcon.png) &#x20;
  &#x20;   \* Click the \*\*View Query Results\*\* link to pivot to the list of assets that were returned by the Base query on the date of Case creation. This initial list of assets is compared to resolved assets in order to determine the progress of the Case.
  \<HTMLBlock>\{\`

  \<div style="background:yellow;padding:10px;text-align:center;">
  (Internal) (Private notes)
  Not in a new tab
  \</div>
  \`}\</HTMLBlock>


  * The green portion of the Progress bar shows the percentage of resolved assets.  &#x20;
    \<HTMLBlock>\{\`

    \<div style="background:yellow;padding:10px;text-align:center;">
    (Internal) (Private notes)
    Clicking it pivots to the list of resolved assets - those assets that were in the initial query, but have since been resolved, and therefore are no longer returned by the query.&#x20;
    Doesn't work.
    \</div>
    \`}\</HTMLBlock>


    * &#x20;  The gray portion of the Progress bar shows the percentage of unresolved assets.  &#x20;
      \<HTMLBlock>\{\`

      \<div style="background:yellow;padding:10px;text-align:center;">
      (Internal) (Private notes)
      Clicking it pivots to the list of unresolved assets - those assets that remain from the initial query.
      Doesn't work.
      \</div>
      \`}\</HTMLBlock>

      ::: info (Note:)
      When pivoting to assets after the date of Case creation, it is likely that there are less assets than were in the initial query, as they may have since been removed from the system (as assets are constantly being correlated and deleted in the system over time). If you want to display on the Assets page all assets that existed at the time that the Case was created, you can \[change \*\*Display by Date\*\* on the Assets page]\(/docs/asset-profile-page#displaying-historical-data) to that date.&#x20;
      :::



### Editing Case Details

In the Case drawer of any Case, you can modify the configuration of the Case. You cannot modify the **Created On** date or the **Base Query**.


**To edit Case information**

1. In the [**Case Management** page](/docs/case-management-page) , click a Case. The Case drawer opens (see screen in [Viewing Case Details](#viewing-case-details)  above).
   1. ![](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/PencilEditIcon.png)

## Viewing Case Assets

Within the **Case Assets** tab of the **Case** drawer, you can view a list of assets associated with a Case was opened and pivot to the main Assets page for detailed information on these assets.



**To view Case assets**

1. On the [**Case Management** page](/docs/case-management-page) , click a specific Case to see.
   2. In the **Case** drawer that opens, click the **Case Assets** tab. The **Case Assets** page opens, with the relevant Case assets listed under the tab corresponding to their main Asset Type (e.g., Devices, Users, Vulnerabilities).\
      ![](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/CaseAssets.png)


### Case Assets Table Details

The table within the Case Assets drawer presents a list of assets (displaying the maximum number that fits in the drawer) on which the Case was created, along with the following fields:

* **Adapter Connections** - Icons representing the adapter connections. Click the arrow at the start of an Asset row to expand and view details per adapter connection.
  * &#x20;\*\*Resolved Date\*\* - The date an asset was identified as handled within this Case. This date reflects when the Case's progress percentage increased due to this asset being resolved. This field remains empty if the asset has not yet been resolved as part of this Case.  &#x20;
    \<HTMLBlock>\{\`

    \<div style="background:yellow;padding:10px;text-align:center;">
    (Internal) (Private notes)

    * **Related Ticket** - The name of the ticket associated with the Case asset. Clicking this name link opens the corresponding Ticket profile page.- **Ticket ID** - The unique identifier of the ticket related to the Case asset.
      * ```
        ```

### Viewing Case Assets on Assets Page

From the **Case Assets** tab in the Case drawer, click the **Open in Asset Page** link to pivot to the Assets page showing the list of assets related to the Case. The Assets page opens, listing the complete list of assets related to the Case.

* Click the Refresh icon near the **Last updated** date and time to ensure that you are seeing the most current list of assets.
  * In this dedicated Assets page, there are two additional columns to the right of **Asset Name**, beyond the standard columns found on any Assets page:- **Linked Tickets: Case Name** - Shows the name of the Case related to the asset.
    - **Linked Tickets: Case ID** - Shows the unique ID of the Case connected to the asset.
      ::: info (Note:)
      These fields only contain values if the Case is part of a Cases Set.\
      :::
    * See [what you can do on an Assets page](https://docs.axonius.com/pl/docs/working-with-assets-pages) .

      ::: info (Note:)
      * Verify that [Historical Snapshot Retention Settings](https://docs.axonius.com/docs/configuring-retention-settings)  are enabled.
        * When you pivot to the assets list, it lists the assets at the time that the Case was created (based on a historical snapshot from the time of the alert). As assets are constantly added, deleted, and correlated over time in the system, it is possible that some assets that were in the original list may no longer be in the system. Change the date to the current date from the **Display by Date** field (above figure - enclosed in red rectangle) to view a current up-to-date asset list.\
          :::
