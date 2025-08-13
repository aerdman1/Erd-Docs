---
title: test123
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---

<HTMLBlock>{`
<div style="background:yellow;padding:10px;text-align:center;">
(Internal) (Private notes)
Fill in the sections that are relevant. At the end of the release delete sections which did not have updates and this note too. Add a link to this in the 7.0 RN and make the latest version of this doc the first one in the list of the minor RNS. URL of pages must be  whats-new-in-axonius-xxx. When the 3 digits are the numbers of the minor version e.g. 7.1.3. For major versions use 2 zeros e.g. 710
</div>
`}</HTMLBlock>

#### Release Date: August 17th 2025

These Release Notes contain new features and enhancements added in version 7.0.5.
* Read [**What's New in Axonius 7.0**](/docs/whats-new-in-axonius-700) to see all Axonius 7.0 features.
  
 
 ##  Cyber Assets New Features and Enhancements
 The following new features and enhancements were added to Axonius Cyber Assets:
 
###     Devices Page New Features and Enhancements
   The following new features and enhancements were added to the **Devices**  page.

   
###   feature
 

### feature

 
###  Users Page New Features and Enhancements
   The following new features and enhancements were added to the  **Users** page.

   
###   feature
 

### feature
 
 
##  SaaS Applications New Features and Enhancements
 The following new features and enhancements were added to SaaS Applications:
 
##  Exposures New Features and Enhancements
 The following new features and enhancements were added to Exposures:

##  Identities New Features and Enhancements
 The following new features and enhancements were added to Identities:
 
 
##  Software Assets   New Features and Enhancements
 The following new features and enhancements were added to Software Assets:
 

 
 

 
##  Axonius Platform New Features and Enhancements
### Dashboard New Features and Enhancements
The following new features and enhancements were added to the Dashboards:

### Dashboard Management Enhancements

### Dashboard Navigation Enhancements

 
 
#### feature
Capability was added to       This enables the following:
*   

#### feature

* Capability was added  to create 

#### feature
 
  

####  feature

### Chart Enhancements

:::

*   
### New and Updated Dashboard Templates

#### feature

 

### Assets Pages
The following features were added to all assets pages:

 

###  Query Wizard Enhancements
### feature  

 

###  feature

 
 

 

 

### Asset Graph New Features and Enhancements

###  Query Management New Features and Enhancements

The following new features and enhancements were added to the Queries:

### Feature name
 

###  Feature name

 
 
  

###  Query feature

 

### Findings Center New Features and Enhancements

##  Enforcement Center New Features and Enhancements
The following new features and enhancements were added to the Enforcement Center:

 ### Dynamic Value Statement Updates
   
The following updates were made to the Dynamic Value statement functionality:

* **generate_string** function - The **generate_string** function can be used in a Dynamic Value statement to create a secure, random string of a specified length and character composition. 
Its syntax is **generate_string (Length, Character Mode)**
Where

    * **Length** - The total number of characters in the generated string (default: 16). 
    * **Character Mode**- **alphanumeric** (default), **hex**, **letters**, or **numbers**).

### Enforcement Sets

 
#### description

 
 
####   feature

### Workflows
#### New Generic Webhook Event Node
A new Generic Webhook Event node can now be added to a Workflow, giving users greater flexibility to integrate with any external system.

Previously, workflows relied on predefined event sources, which complicated connecting to tools with custom data formats. This new node simplifies integrations by allowing users to:

*  Receive data from any external system via a webhook. 
*  Automatically parse incoming payloads in various formats (JSON, form data, etc.).
*  Dynamically extract specific fields for use in subsequent workflow nodes.

This enhancement broadens integration possibilities and simplifies the setup process, especially when working with custom APIs and third-party tools.
 
  ### Dynamic Value Statement Updates
   
   The following updates were made to the Dynamic Value statement functionality:
#### HTML and Plain Text Editor
The new editor allows you to create and format custom messages within a Dynamic Value statement using Plain Text or raw HTML code. This is typically used to generate custom email bodies, reports, or other text output combining rich formatting and dynamic data.

###   Enhancements to Axonius Actions
 
 
###   feature

### Cases New Features and Enhancements
The **Create a Case Set** wizard now enables triggering automated **Workflows** directly from the **Add Actions** step. This new feature applies specifically to event-based scenarios, such as when an asset is no longer part of a Case query or when a ticket's status changes. The workflow's triggering event is preconfigured to match the selected condition and cannot be replaced, ensuring it is automatically initiated by the correct event without any manual setup.
![AddWorkflowConditions.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AddWorkflowConditions.png)

### Reports New Features and Enhancements
The following enhancements were added to reports.

### Adapter Pages and Adapter Interface New Features and Enhancements

The following updates were made to the standard functionality across all adapters:

###  Adapter Interface
 
#### New Adapter Ingestion Rule trim_regex Post Action 
The new *trim_regex* post action can be used to remove a specific string or pattern from a field using regex patterns. This enables cleaning up or standardizing data by removing unwanted text. 
For example, it can be used to remove the MAC address (and the preceding dash) from the end of an **Asset Name** and **Host Name** fields.

**Syntax:**
```
trim_regex [field] [regex_template] 
```

* [field] - The target field from which to remove the string.

* [regex_template] - The regex pattern that identifies the string to be removed. 

####  Adapter Advanced Settings
The following setting was added to the **Adapter Configuration** section in [Advanced Settings](/pl/docs/advanced-settings):

* Added the capacity to set a threshold time (in hours) that will terminate a running successful fetch operation of an adapter when its fetch exceeds the time set (including an appropriate log and status). This will allow you to manage the duration of the discovery cycle, ensuring that even successful fetches stay within the planned time frame.

#### Adapter Connections

* The "Terminate after X hours of an active fetch" field was added to the [Adapter Connections](/pl/docs/adapter-connections) page.

  

 
### Activity Log New Features and Enhancements

###  Node Page New Features and Enhancements

### System Settings New Features and Enhancements
 The following updates were made to various System settings:
 
### Feature
 

### Feature name
 
 
###  Feature
 
### New Permissions
 

 
 

 

## General Updates
generally not relevant....

### Feature Name
feature name
 

   
   

    
##  Cloud Asset Compliance New Features and Enhancements
The following updates were made to  [Axonius Cloud Asset Compliance](/docs/cloud-asset-compliance-page):

## Axonius-hosted (SaaS) Deployments New Features and Enhancements
###  feature

### feature   
 

## Adapter and Enforcement Action Updates

### New Adapters
 The following new adapters were added:

*  [**ManageEngine EventLog Analyzer**](/pl/docs/manage-engine-event-log-analyzer)
    *  ManageEngine EventLog Analyzer is a web-based SIEM solution that provides real-time log monitoring, threat detection, compliance reporting, and forensic analysis across diverse IT environments. (Fetches: Devices)
*  [**Recorded Future Attack Surface Intelligence**](/pl/docs/recorded-future-asi)
    *  Recorded Future Attack Surface Intelligence maps and monitors your exposed digital assets in real time, helping you proactively reduce risk — unlike the core platform, which focuses on external threats, this tool reveals your attack surface from an attacker’s perspective. (Fetches: Devices, Vulnerabilities, SaaS Applications)
*  [**ThreatMon**](/pl/docs/threat-mon)
    *  ThreatMon is a platform that provides cyber intelligence for monitoring and analyzing potential threats. (Fetches: Alerts/Incidents)

 
 
 ### Adapter Updates
 The following adapters were updated:
  * [**Ceridian Dayforce**](/pl/docs/ceridian-dayforce) - Added the option for the adapter to automatically detect the new URL in the error message and use it to update the **Host Name or IP Address** field in the adapter's connection.
 * [**Dell PowerStore**](/pl/docs/dell-power-store) - Added the option to fetch NFS server assets.
 * [**Elasticsearch**](/pl/docs/elasticsearch) - Added the option to fetch users instead of devices if logs contain user data.
 * [**Infoblox DDI**](/pl/docs/infoblox) - This adapter now supports Layer7 API Gateway connection.
 * [**IONIX (formerly Cyberpion)**](/pl/docs/ionix) - This adapter now fetches Domains & URLs and Application Services as assets (and no longer fetches Devices).
 * [**OneTrust**](/pl/docs/one-trust) - This adapter now supports Layer7 API Gateway connection.
 * **Oracle Netsuite** - When the option to fetch vendor payment details is enabled, it is now possible to specify the look-back period for fetching transactions. Only vendor payments published within this many days of the current date will be retrieved.
 * [**Palo Alto Networks Cortex XSOAR**](/pl/docs/paloalto-xsoar) - Added the option to choose between API v6 and API v8 in the connection parameters.
 * [**ServiceNow**](/pl/docs/servicenow) - The [Custom Parsing](/pl/docs/adapter-custom-parsing) capability now supports Users as well.
 * [**Tenable.sc (SecurityCenter)**](/pl/docs/tenablesc-formerly-securitycenter) - Added the option to fetch software name for CVEs associated with Plugin ID 63155.
 * [**Venafi**](/pl/docs/venafi) - Added the option to parse devices that have CertificateDetails only under Certificates (and not as Devices).
 
 
 ###  New Enforcement Actions
The following Enforcement Actions were added:
* [**Monday - Manage Users**](https://docs.axonius.com/enforcements/docs/monday-manage-users) - Performs the following actions on users: 
    * Activate User
    * Deactivate User
    * Update User Role
    * Delete User from Workspace
* [**NAVEX - Create User**](https://docs.axonius.com/enforcements/docs/navex-create-user) - Creates new users in NAVEX.
* [**NAVEX - Delete User**](https://docs.axonius.com/enforcements/docs/navex-delete-user) - Deletes users from NAVEX.
* [**NAVEX - Assign User Group**](https://docs.axonius.com/enforcements/docs/navex-assign-user-group) - Assigns users to a group in NAVEX.
* [**NAVEX - Update User Details**](https://docs.axonius.com/enforcements/docs/navex-update-user-details) - Updates the user's group in NAVEX.

###  Updated Enforcement Actions
The following Enforcement Actions were updated: 

 ###  New Events
The following Events were added:

###  Updated Events
The following Events were updated:
