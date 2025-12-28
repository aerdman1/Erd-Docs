---
title: Artifcatory test123
deprecated: false
hidden: false
icon: far fa-arrows-maximize
link:
  new_tab: false
metadata:
  robots: index
---
This section includes all the Artifactory 7.117 releases.

## Artifactory 7.117.19 Self-Hosted (Self-Managed)

Released: 23 October 2025

#### Resolved Issues

| JIRA Issue  | Component | Severity | Description                                                                                                                                                                                                             |
| :---------- | :-------- | :------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RTDEV-63859 | General   | Medium   | Fixed an issue whereby a virtual RPM repository was unable to merge metadata when it contained an upstream remote RPM repository with Zstandard compression index files and a local repository containing RPM packages. |
| RTDEV-62683 | General   | Medium   | Fixed an issue whereby it was not possible to display HTML contents of a zip file if the zip file name contained the German umlaut character (for example, `ä`).                                                        |
| JFUI-18972  | General   | Medium   | Fixed an issue whereby configuring log rotation for Frontend metrics logs in Artifactory's `system.yaml` file did not work, as the logs failed to rotate after a service restart.                                       |

## Artifactory 7.117.18 Self-Hosted

Released: 7 October 2025

#### Feature Enhancements

* **Maintenance Release**

  Released a fix for CVE-2025-41249. For more information see [CVEs Not Impacting Artifactory](/docs/cves-not-impacting-artifactory).

#### Resolved Issues

| JIRA Issue | Component       | Severity | Description                                                                                                                                  |
| :--------- | :-------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| JA-17875   | User Management | High     | Fixed an issue with the Projects user REST API, where a project admin received a 403 error when attempting to retrieve project user details. |

## Artifactory 7.117.17 Self-Hosted

Released: 24 September 2025

#### Resolved Issues

| JIRA Issue  | Component           | Severity | Description                                                                                                                                                                       |
| :---------- | :------------------ | :------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| TOPO-627    | User Interface (UI) | Medium   | Fixed an issue related to the Service Status page in the JFrog Platform WebUI did not display the Uptime value for the Topology service.                                          |
| RTDEV-61792 | General             | Medium   | Fixed an issue whereby the OCI referrers.json file was not updated after the distribution of an already existing image.                                                           |
| RTDEV-63240 | Packages            | Medium   | Fixed an issue whereby, copying or moving a Debian package to a path where a package with the same filename but a different checksum already existed caused metadata duplication. |

## Artifactory 7.117.16 Self-Hosted

Released: 16 September 2025

#### Resolved Issues

| JIRA Issue  | Component                    | Severity | Description                                                                                                                                              |
| :---------- | :--------------------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RTDEV-62097 | Packages                     | Medium   | Fixed an issue whereby a 404 error was received from a request for a package that used a "If-None-Match" header.                                         |
| RTDEV-61672 | Release Lifecycle Management | Medium   | Fixed an issue whereby publishing build-info with an empty statuses section caused a 500 error.                                                          |
| RTDEV-61647 | Archiving/Cold Storage       | Medium   | Fixed an issue whereby inconsistent naming and compression format for artifactory-cleanup-audit logs caused sync failures and misclassification of logs. |
| RTDEV-61500 | Archiving/Cold Storage       | Medium   | Fixed an issue whereby a cleanup policy would stop running when encountering certain directories.                                                        |
| JA-18037    | User management              | High     | Fixed an issue whereby clicking Unlock on the Edit Profile page was throwing a 403 Forbidden error.                                                      |
| INST-12162  | Installation                 | Medium   | Fixed an issue where the readOnlyRootFilesystem breaks the functionality of the /app directory.                                                          |

## Artifactory 7.117.15 Self-Hosted

Released: 2 September 2025

#### Resolved Issues

| JIRA Issue  | Component              | Severity | Description                                                                                                                                                                                                                       |
| :---------- | :--------------------- | :------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EVT-1706    | General                | Medium   | Fixed an issue whereby a webhook would fail if any of the repositories it was configured to listen to were deleted from the system.                                                                                               |
| RTDEV-60865 | General                | Medium   | Fixed an issue whereby when Artifactory attempted to authenticate a remote Sonatype Nexus repository using Basic Authentication, the request failed with a 401 Unauthorized error if the username contained non-ASCII characters. |
| RTDEV-61861 | Packages               | Critical | Fixed an issue whereby cleanup policies were incorrectly deleting Helm packages with the same prefix name.                                                                                                                        |
| RTDEV-56935 | Packages               | Medium   | Fixed an issue whereby after saving an NIM remote repository configuration, the test connection failed.                                                                                                                           |
| RTDEV-61184 | Packages               | Medium   | Fixed an issue whereby Artifactory was not able to cache the the drupal/nouislider_js module and other modules from git.drupalcode.org.                                                                                           |
| RTDEV-62449 | Packages               | Medium   | Fixed an issue whereby passing the X-JFrog-Override-Base-URL header during npm install process from a virtual repository might not be respected.                                                                                  |
| RTDEV-61165 | Repositories           | Medium   | Fixed an issue whereby the Get All Repository Configurations API, in certain cases, returned an empty response when using the JSON accept header.                                                                                 |
| RTDEV-61643 | Storage                | Medium   | Improvements were made in thread synchronization in sharding and s3-sharding providers.                                                                                                                                           |
| RTDEV-62157 | Federated Repositories | High     | Fixed an issue that caused the Federation to fail if a proxy was defined at the platform level but the Federated repository was set to `no_proxy`.                                                                                |

## Artifactory 7.117.14 Self-Hosted

Released: 19 August, 2025

#### Resolved Issues

| JIRA Issue  | Component                    | Severity | Description                                                                                                                                                                                                                                                   |
| :---------- | :--------------------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| RPG-1841    | General                      | Critical | Fixed an issue whereby upgrading existing Artifactory HA installations may fail due to the Router service not starting.                                                                                                                                       |
| JFUI-18900  | General                      | Medium   | Fixed an issue whereby a custom message enabled in the UI would cause the "The Federated repository settings are not synchronized between these repositories" notification to negatively impact the user experience by expanding and blocking other elements. |
| INST-12162  | Installation                 | Medium   | Fixed an issue whereby the `readOnlyRootFilesystem` was breaking the functionality of the `/app` directory.                                                                                                                                                   |
| RTDEV-59071 | Packages                     | Medium   | Fixed a bug whereby an external user can get an API key instead of an Identity token in Maven SetMeUp tool.                                                                                                                                                   |
| RTDEV-61351 | Release Lifecycle Management | Medium   | Fixed an issue whereby adding two content-identical images with different tags to a release  bundle would result in one of the images being dropped.                                                                                                          |
| RTDEV-59159 | Repositories                 | Low      | Fixed an issue whereby attempts to test the connection to a remote repository using token authentication fail.                                                                                                                                                |
| RTDEV-57893 | User Interface (UI)          | Medium   | Fixed an issue whereby artifacts failed to appear in the UI browser after defining an include pattern on the virtual repository.                                                                                                                              |

## Artifactory 7.117.12 Self-Hosted

Released: 5 August, 2025

#### Resolved Issues

| JIRA Issue  | Component              | Severity | Description                                                                                                                           |
| :---------- | :--------------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| RTDEV-58782 | Archiving/Cold Storage | Medium   | Fixed an issue whereby a project admin could not successfully call the Get all Package Cleanup Policies API and received a 403 error. |
| RTDEV-60343 | Packages               | Medium   | Fixed an issue whereby Conan federation did not sync all package properties.                                                          |

## Artifactory 7.117.10 Self-Hosted

Released: 31 July 2025

#### Resolved Issues

| JIRA Issue | Component       | Severity | Description                                                                                                                                  |
| :--------- | :-------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| JA-17875   | User Management | High     | Fixed an issue with the Projects user REST API, where a project admin received a 403 error when attempting to retrieve project user details. |

## Artifactory 7.117.8 Self-Hosted

Released: 29 July 2025

<Callout icon="⚠️" theme="warning">
  **Known Issue in this Version**

  During startup and regular operation, the Artifactory Frontend service attempts to download resources from the public internet endpoint `https://grpc.qwak.ai` .Therefore, JFrog recommends avoiding the upgrade to this version if your organization's environment restricts access to this endpoint. For more information, see [Artifactory Known Issues](/docs/artifactory-7-117).
</Callout>

#### Resolved Issues

| JIRA Issue | Component | Severity | Description                                                                                                                                             |
| :--------- | :-------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| JFMC-6021  | General   | High     | Fixed an issue caused by <Anchor label="CVE-2025-53506" target="_blank" href="https://nvd.nist.gov/vuln/detail/CVE-2025-53506">CVE-2025-53506</Anchor>. |

## Artifactory 7.117.7 Self-Hosted

Released: 25 July 2025

<Callout icon="⚠️" theme="warning">
  **Known Issue in this Version**

  During startup and regular operation, the Artifactory Frontend service attempts to download resources from the public internet endpoint `https://grpc.qwak.ai` .Therefore, JFrog recommends avoiding the upgrade to this version if your organization's environment restricts access to this endpoint. For more information, see [Artifactory Known Issues](/docs/artifactory-7-117).
</Callout>

#### Resolved Issues

| JIRA Issue | Component                | Severity | Description                                                                                                                                                                                |
| :--------- | :----------------------- | :------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| JA-17727   | Authentication Providers | Low      | Fixed an issue whereby authenticate attempts using invalid tokens caused temporary login suspension. Only basic credentials authentication attempts should count towards login suspension. |
| RPG-1831   | General                  | High     | Fixed an issue whereby upgrading existing Artifactory installations with Router TLS enabled may fail due to the Router service not starting.                                               |

## Artifactory 7.117.5 Self-Hosted

Released: 24 July 2025

#### New Features

<Callout icon="⚠️" theme="warning">
  **Known Issues in this Version**

  * During startup and regular operation, the Artifactory Frontend service attempts to download resources from the public internet endpoint `https://grpc.qwak.ai` .Therefore, JFrog recommends avoiding the upgrade to this version if your organization's environment restricts access to this endpoint. For more information, see [Artifactory Known Issues](/docs/artifactory-7-117).
  * When upgrading existing Artifactory installations that have Router TLS enabled (`router.tlsEnabled: true`) in the `system.yaml` file, a common issue has been identified. The upgrade process might fail because the Router service fails to start, displaying the following error: _Error during the build of the default TLS configuration: unknown TLS options: default_. For more information, see [Artifactory Known Issues](/docs/artifactory-7-117).w
</Callout>

<Callout icon="⚠️" theme="warning">
  **Breaking Change for Access REST APIs**

  From this version, Access REST API responses will be returned as compact JSON and not as pretty-printed JSON. Note that some automatic parsers that rely on the formatting will require an update.
</Callout>

* **New REST API: Get Projects List for a Global Role**

  The JFrog Platform now supports getting a paginated list of projects where a specific global role is used. For more information, see [Get Project List for a Global Role](/docs/artifactory-7-117-cloud).

#### Feature Enhancements

<Callout icon="⚠️" theme="warning">
  **Breaking Change for Artifactory Federation Service**

  The version of the [Artifactory Federation Service](/artifactory/docs/artifactory-federation-service) (RTFS) that comes with this Artifactory release changes the context path from **/artifactory/service/rtfs** to /**rtfs**. This is a breaking change for users who have multiple sites (JPDs) using RTFS. (Users who run RTFS on only one site, and sites that use the legacy Federation service, are unaffected by this change.)

  Users in Self-Hosted environments who have sites running an older version of RTFS should upgrade them to the new version of RTFS as soon as possible to accommodate the new context path. As an interim solution, a set of commands can be added as a workaround to bridge the context path differences between sites using the new version of RTFS and sites using an older version, as described below.

  ##### Nginx Configuration

  Add this command to the Nginx configuration of a site using the **new** version of RTFS:

  ```
  location /artifactory/ {
      if ($request_uri ~ ^/artifactory/service/rtfs/(.*) $ ) {
        proxy_pass       http://router/rtfs/$1;
        break;
      }
      if ( $request_uri ~ ^/artifactory/(.*) $ ) {
        proxy_pass       http://artifactory/artifactory/$1;
      }
      proxy_pass         http://artifactory/artifactory/;
    }
  ```

  This command instructs Nginx to redirect requests from sites that use the old RTFS context path to the new context path.

  Add this command to the Nginx configuration of a site using the **old** version of RTFS:

  ```
  location /rtfs/ {
    if ($request_uri ~ ^/rtfs/(.*) $ ) {
        proxy_pass       http://router/artifactory/service/rtfs/$1;
        break;
      }
  ```

  This command instructs Nginx to redirect requests from sites that use the new RTFS context path to the old context path.

  ##### Apache Configuration

  Use the following Apache rewrite rule to redirect requests between sites that have a mix of old and new context paths:

  ```
  RewriteRule "^/artifactory/service/rtfs/(.*) $" "balancer://artifactory/artifactory/service/rtfs/$1" [P,L]
  ```

  ##### Important Migration Note

  When [migrating](/artifactory/docs/migrate-to-the-artifactory-federation-service) from the legacy Federation service to RTFS, be sure to use **version 2.0** of the CLI, which implements the new context path.
</Callout>

* **Release Bundles**

  * **Create Release Bundle v2 version from multiple sources**

    You can now create a Release Bundle v2 version from multiple sources, for example, a combination of artifacts, builds, and existing Release Bundles. For more information, see [Create Release Bundle v2 Version](/docs/599359#UUID-0af058a6-d1b4-3125-a0ca-4a8d673ddda5).

  * **Create a Release Bundle v2 version from packages**

    You can now create a Release Bundle v2 version by defining one or more packages to include in the Release Bundle. The Release Bundle can include packages of every type supported by Artifactory. For more information, see [Create Release Bundle v2 Version](/docs/599359#UUID-0af058a6-d1b4-3125-a0ca-4a8d673ddda5).

  * **Create a Release Bundle v2 version using items in remote-cache repositories**

    You can now create a Release Bundle v2 version that includes packages and artifacts located in <Anchor label="remote-cache" target="_blank" href="https://jfrog.com/help/r/artifactory-why-artifacts-are-not-listing-in-tree-view-for-my-remote-repository/difference-between-remote-and-remote-cache-repositories">remote-cache</Anchor> repositories. For more information about Release Bundle creation, see [Create Release Bundle v2 Version](/docs/599359#UUID-0af058a6-d1b4-3125-a0ca-4a8d673ddda5).

  * **SBOMs containing remote-cache dependencies**

    Release Bundle v2 versions created from [build-info](/integrations/docs/about-build-info) can now include build dependencies located in remote-cache repositories, provided you have used the option for including dependencies in the Release Bundle. If this option has not been used, the remote-cache dependencies will not be included in the Release Bundle, but the SBOM used by Xray will still contain metadata about those dependencies.

  * **Release Bundle v2 – support for SBOMs with remote dependencies**

    Previously, Release Bundle v2 did not include information about dependencies from remote repositories, which prevented the generation of a complete SBOM (software bill of materials) by Xray. This limitation hoas now been removed, which means that information about these dependencies will be included in the SBOM, and Xray (version 3.121.7 and above) can scan them. Having a complete SBOM increases transparency and security by providing insight into all components involved in the Release Bundle, and helps with auditing and compliance.

<Callout icon="📘" theme="info">
  **Note**

  Although information about remote dependencies is included in the SBOM, the dependencies themselves are not included in the Release Bundle in the current version.
</Callout>

* **Source environment of Release Bundle v2 promotions**

  The source environment of a Release Bundle v2 promotion is now included in the API response, making it easier for users to identify the start and end points of the promotion. For more information about promotion, see [Promote Release Bundle v2 Version](/docs/artifactory-7-116).

* **Adding properties to Release Bundle v2 versions**

  You can now add [properties](/artifactory/docs/add-properties-to-items) and [property sets](/artifactory/docs/create-property-set) to Release Bundle v2 versions. Properties are user-defined, key-value pairs that are added to the Release Bundle v2 version's manifest file. For more information, see [Add Properties to a Release Bundle v2 Version](/governance/docs/add-properties-to-a-release-bundle-v2-version).

* **New search and filtering options for Release Lifecycle Management kanban board**

  The Release Lifecycle Management kanban board now features options for searching through and filtering the displayed Release Bundle versions. These options make it easier for you to focus on the versions of greatest interest.

* **Release Bundle v2 promotion rollback**

  You can now use the [REST API](/docs/artifactory-7-117-cloud) to roll back the latest promotion of a Release Bundle v2 version. Rollback deletes the contents of the latest promotion (including its artifacts, properties, and evidence) and restores the version to its previous environment, including the properties and evidence it contained when the version was first created. For more information, see [Promotion Rollback](/governance/docs/promotion-rollback).

* **Release Bundle v2 version supports plus sign character**

  You can now include a plus sign (+) when defining the version of a Release Bundle v2. This change was made to achieve alignment with the SemVer 2.0.0 specification. For more information, see [Create Release Bundle v2 Version](/docs/599359#UUID-0af058a6-d1b4-3125-a0ca-4a8d673ddda5).

* **Assigning a tag when creating a Release Bundle v2 version**

  You can now assign a tag when creating a Release Bundle v2 version with the [REST API](/docs/599359#UUID-0af058a6-d1b4-3125-a0ca-4a8d673ddda5). Use the tag to identify the version quickly. For example, you can create tags such as nightly-build, release-candidate, bugfix-2025-33124, and so on. The tag will appear on the card for the Release Bundle version on the Release Lifecycle stages board.

<Callout icon="📘" theme="info">
  **Note**

  You can continue using the [Assign Tag](/docs/artifactory-7-111-cloud) REST API to tag existing Release Bundle versions.
</Callout>

* **Version counter on Release Lifecycle stages board**

  The Release Lifecycle stages board now includes a counter so that you can see at a glance how many versions of the selected Release Bundle currently exist.

* **Improved error codes during Release Bundle v2 creation**

  Artifactory will now return 404 when an artifact or package is missing from the defined artifact or package list during Release Bundle v2 creation. In addition, Artifactory will return 403 when an artifact or package is filtered out due to a user permissions issue.

* **Evidence provider logo displayed on stages board**

  Each evidence item displayed on the Release Lifecycle stages board now includes a logo to indicate the provider of that evidence, whether it is evidence provided by the JFrog platform or evidence originating from other providers, such as GitHub or Sonar. The logo is also displayed prominently when the contents of the evidence item are opened.

* **Cleanup and Retention Policies**

  * **Support for Composer Packages in Cleanup Policies and Smart Archiving**

    Cleanup Policies and Smart Archiving now support Composer package type.
  * **Support for Chef and Puppet Packages in Cleanup Policies**

    Cleanup Policies now support Chef and Puppet package types.
  * **Support for N versions in Retention Policies**

    Cleanup Policies and Smart Archiving now support N versions for Docker, OCI and Helm OCI. For more information, see [Cleanup Supported Packages](/governance/docs/cleanup-supported-packages) and [Smart Archiving Supported Packages](/governance/docs/smart-archiving-supported-packages).
  * **API Run Summary Reports for Cleanup and Smart Archiving**

    Added new API endpoints for cleanup and smart archiving that provide detailed run summary reports in JSON format. For more details, refer to[View Package Cleanup Policy Run Summary Report API](/docs/artifactory-7-117-cloud) and [View Smart Archiving Policy Run Summary Report API](/docs/artifactory-7-117-cloud).
  * **Smart Archiving Packages: Evidence**

    Added support for the archival of evidence associated with any packages. This enhancement ensures that relevant evidence is preserved as part of your archiving strategy, streamlining your package management process. For more information, refer to [Smart Archiving](/governance/docs/smart-archiving).
  * **Property-based Policy Condition - Smart Archiving Packages**

    Enhanced package-archivie functionality with the addition of a property-based policy condition. You can now include or exclude specific package versions from archive by applying a property-based policy condition. This allows for more granular control over which packages are retained or archived during archive actions. For more information, see [Create Smart Archiving Policy](/governance/docs/create-smart-archiving-policy).

* **Packages and Repositories**

  * **Default Socket Timeout for Federated Repositories**

    The default socket timeout for Federated repositories has been changed to 300000 milliseconds (5 minutes). This value can be adjusted, if required, using an Artifactory system property. For more information, see Increase the Predefined Socket Timeout for Larger Repositories.

  * **CocoaPods Smart Repositories**

    The **CocoaPods Settings** section has been removed from the smart repository creation page. Smart repositories automatically inherit configuration from their source repository, making manual settings unnecessary.

  * **Cocoapods CDN Smart Repository Support**

    Added smart repositories support for CocoaPods CDN.

  * **Improvement in Promoting Docker Images**

    Starting from this Artifactory version, when Docker image promotion overrides an existing image tag in the target repository, shared layers from other tags of the same image will not be deleted. In versions prior to 7.117.1, these shared layers may be deleted.

  * **Support for Oracle 23c**

    Artifactory is now certified to work with the Oracle 23c database.

  * **Improved Get Federation Sync State REST API performance**

    The performance of the [REST API](/docs/606137#UUID-16223486-d3b5-f0af-64b9-d509adad0731) that returns the synchronization state of all Federated repositories in the JPD has been improved.

<Callout icon="📘" theme="info">
  **Note**

  This API endpoint is relevant for users operating the legacy Federation service, not the [Artifactory Federation Service](/artifactory/docs/artifactory-federation-service) (RTFS).
</Callout>

* **JFrog Platform**

  * **Removal and Backup of Mission Control Plugins**

    The following Mission Control plugins, which were created during the initial days specifically for Mission Control, are no longer required by any JFrog products. As a result, these plugins will be removed in this version and backup files are created with a `.backup` extension.

    * `internalUser.groovy`
    * `ldapSettingsConfig.groovy`
    * `ldapGroupsConfig.groovy`
    * `haClusterDump.groovy`
    * `repoLayoutsConfig.groovy`
    * `proxiesConfig.groovy`
    * `propertySetsConfig.groovy`
    * `requestRouting.groovy`
    * `httpSsoConfig.groovy`
    * `pluginsConfig.groovy`

    For more information, see [User Plugins](/governance/docs/user-plugins) documentation.
  * **Support for Reading Permissions Scoped Tokens**

    It is now possible for non-admin users to use the [Get Projects List](/projects/docs/project-management-tasks), [Get Project Users](/projects/docs/project-user-management-tasks), [Get Repository Configuration](/docs/artifactory-7-117-cloud) , [HA License Information](/docs/artifactory-7-114) , and [Get Storage Summary Info](/docs/artifactory-7-114) endpoints using a scoped token. For more information, see [Create Scoped Token](/docs/774543#UUID-899599c4-3b27-ae26-6ca4-78695577996e).
  * **Secure Cloud Storage Credentials in Helm**

    We have introduced a new feature that allows you to supply cloud storage identity and credentials as a Kubernetes secret within your `values.yaml` file for Artifactory Helm deployments. This capability extends to:

    * AWS S3V3: Securely provide your AWS S3V3 access keys and secret keys.
    * Azure Blob Storage: Securely provide your Azure storage account name and access key.
  * **Improved Builds table**

    The Builds table features two important enhancements:

    * The maximum of 100 builds displayed in the table has been removed. The table can now display all the builds that exist in your Artifactory instance.
    * A search window has been added to make it easier to focus on the builds of greatest importance to you. (This new search window works in coordination with the platform search window at the top of the UI.)
  * **Additions to Artifactory Request Log (JSON version)**

    The JSON version of the Artifactory request log has been enhanced to include additional metrics for improved tracking of request and response performance. These enhancements provide insights into response timing, data size, processing duration, and request specifications.
  * **Expanded support for scoped tokens in Deploy Evidence API**

    The [Deploy Evidence](/governance/docs/evidence-service-cli) REST API now supports scoped tokens based on specified artifacts in addition to its previous support for scoped tokens based on a specified repository. In both cases, the scoped token must include the Annotate action. For more information, see [Create Scoped Token](/docs/774543#UUID-899599c4-3b27-ae26-6ca4-78695577996e).
  * **Filter Users and Groups by Role Within a Repository Via REST API** The JFrog Platform now supports filtering users and groups by role within a specific repository via REST API. For example, you can easily retrieve a list of admins for a specific repository to streamline permissions management. For more information, see [Get User List](/docs/artifactory-7-117-cloud) and [Get a List of Groups](/docs/artifactory-7-117-cloud).
  * **Allow Granting Manage Permissions in Permissions V2**

    The JFrog Platform now supports allowing users with `manage` permissions to grant `manage` and other permissions to other users in Permissions V2, although it is not recommended. For more information, see [Permissions](/governance/docs/permissions).
  * **Add Unlimited Groups to a Reference Token in SAML** The JFrog Platform now supports adding an unlimited number of groups in SAML user-scoped reference tokens, as the number of groups does not affect the payload. For more information, see [Create Token](/docs/512478#UUID-806c0225-ea73-b218-3f7f-341c32ebe03b).
  * **Improved Robustness of Binary Uploads to Google Cloud Storage (GCS)**

    The robustness of binary uploads to GCS has been improved by enhancing recovery mechanisms.
  * **Daily Notification Emails for Token Expiration**

    The JFrog Platform now supports setting intervals for email notifications about tokens that are about to expire, either once or daily during the notice period. For more information, see [Token Expiration Notification](/governance/docs/token-expiration).
  * **JFrog Platform WebUI Breadcrumbs**

    From Artifactory version 7.116.3, breadcrumbs allowing you to orient yourself in the JFrog Platform WebUI will gradually be rolled out to all pages. For more information, see [JFrog Platform Navigation](/governance/docs/jfrog-platform-navigation).

* **Workers**

  * **Get Worker Code Samples with Worker Code Gallery**

    The JFrog Platform now supports populating new Workers with GitHub code samples, directly from the JFrog Platform WebUI. For more information, see [Configure Workers in the UI](/governance/docs/configure-workers-in-the-ui).
  * **Rerun Worker Runs**

    The JFrog Platform now supports a Rerun feature to troubleshoot Worker runs. For more information, see [Workers Troubleshooting](/docs/artifactory-7-115).
  * **Updated Type Definitions for Event-Driven Workers' Response**

    Refined TypeScript type definitions for event-driven workers' response to improve the developer experience.

#### Resolved Issues

| JIRA Issue                                                                                                                | Component                    | Severity | Description                                                                                                                                                                                                                                                                                                                                                    |
| :------------------------------------------------------------------------------------------------------------------------ | :--------------------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| JA-7684                                                                                                                   | Archiving/Cold Storage       | Medium   | Fixed an issue whereby SaaS customers were able to execute the Access Export API.                                                                                                                                                                                                                                                                              |
| RTDEV-56961                                                                                                               | Archiving/Cold Storage       | Medium   | Fixed an issue whereby the next token was included in the Maven/Gradle cleanup results even if the number of results was less than the limit.                                                                                                                                                                                                                  |
| JA-16308                                                                                                                  | Authentication Providers     | Medium   | Fixed an issue whereby the JFrog CLI refresh token was failing for non-admin SAML users when their token scope included additional permissions beyond the default.                                                                                                                                                                                             |
| JA-17630                                                                                                                  | Authentication Providers     | Low      | Fixed Fixed an issue where the `access/api/v1/ldap/groups/ldap-groups/refresh?operation=UPDATE_AND_IMPORT` endpoint failed to work correctly when authenticated with an access token. This fix ensures that users can now successfully refresh LDAP groups using an access token.                                                                              |
| RTDEV-56222                                                                                                               | Authentication Providers     | Medium   | Fixed an issue whereby customers could sometimes mistakenly deploy artifacts using a FULL ACCESS TOKEN because the FULL ACCESS TOKEN did not take into account the scoped group of the token.                                                                                                                                                                  |
| RTFE-2989                                                                                                                 | Authentication Providers     | Medium   | Fixed an issue whereby, it was possible to generate a valid token on the Set Me Up page when entering any password in the Password field when logging in by means of Authentication Provider.                                                                                                                                                                  |
| JA-17696                                                                                                                  | Database                     | Critical | Fixed an issue whereby when Artifactory was configured to use a non-public PostgreSQL schema and a **search_path** that included the user's schema (default Postgres setting), Access incorrectly defaulted to using the non-public schema for its tables.                                                                                                     |
| RTDEV-57265                                                                                                               | Evidence Management          | High     | Fixed an issue that prevented users from deleting a repository containing evidence files.                                                                                                                                                                                                                                                                      |
| RTDEV-55125                                                                                                               | Federated Repositories       | Low      | Fixed an issue whereby when using the JMX exporter to see mBean metrics, errors were encountered.                                                                                                                                                                                                                                                              |
| RTDEV-57406                                                                                                               | General                      | Low      | Fixed an issue whereby an error warning was received when converting a RepoDescriptor URL to URI when the upstream URL in the remote repository settings had a ‘/’ at the end of the URL.                                                                                                                                                                      |
| RTDEV-58470                                                                                                               | General                      | Medium   | Fixed an issue whereby when the client requested an incorrect HTTP range, Artifactory returned an invalid HTTP content range.                                                                                                                                                                                                                                  |
| JA-17181                                                                                                                  | General                      | High     | Fixed an issue whereby the OIDC token exchange would fail when the Organization field was set and the Enable Permissive Configuration setting was disabled.                                                                                                                                                                                                    |
| META-1873                                                                                                                 | General                      | Medium   | Fixed an issue whereby metadata was unable to handle non-existent packages requested by Xray.                                                                                                                                                                                                                                                                  |
| RPG-1799                                                                                                                  | General                      | High     | Fixed an issue whereby when upgrading Artifactory in Windows to newer versions, Xray was unavailable.                                                                                                                                                                                                                                                          |
| RTDEV-54362                                                                                                               | General                      | High     | Fixed an issue whereby when calling the zap cache API, the zap repository cache was holding all artifact locks in a single long transaction.                                                                                                                                                                                                                   |
| RTDEV-56440                                                                                                               | General                      | Medium   | Fixed an issue whereby the internal repository **jfrog-usage-logs** was included by default in the system backup, and was excluded from export/import repositories and export/import system flows.                                                                                                                                                             |
| RTDEV-57054                                                                                                               | General                      | Low      | Fixed an issue whereby the Audit Event popup that is displayed in the Curation User Interface was showing a name for the Origin Server that was sometimes a random string of characters, which was not useful to the user.                                                                                                                                     |
| RTDEV-57123                                                                                                               | General                      | Medium   | Fixed an issue whereby when creating or updating properties for a package with an emoji, if the database did not support emojis the action failed with 500 error message and the user was navigated to the 500 error page. Now, the user will receive a 422 error code and the properties will not be created/updated.                                         |
| RTDEV-57267                                                                                                               | General                      | High     | Fixed an issue whereby Artifactory was still picking up the https port for router registration, and did not pick up the port from system configuration.                                                                                                                                                                                                        |
| RTDEV-57293                                                                                                               | General                      | Medium   | Fixed an issue whereby an AQL transitive query on a virtual repository failed and returned a HTTP 500 response when the query was performed on a virtual repository that had an offline remote repository.                                                                                                                                                     |
| RTDEV-57400                                                                                                               | General                      | Medium   | Fixed an issue whereby Artifactory incorrectly displayed an old license expiration date even after a new license key was applied, due to persistent cached entitlements overriding new license information.                                                                                                                                                    |
| <Anchor label="RTFACT-31097" target="_blank" href="https://jfrog.atlassian.net/browse/RTFACT-31097">RTFACT-31097</Anchor> | General                      | Medium   | Fixed an issue whereby, when searching for artifacts using the underscore (_) , the underscore was considered a wildcard and lead to undesirable results. This has been changed so that when using the underscore, it will be treated as an underscore character and not a wildcard.                                                                           |
| <Anchor label="RTFACT-31188" target="_blank" href="https://jfrog.atlassian.net/browse/RTFACT-31188">RTFACT-31188</Anchor> | General                      | Low      | Fixed an issue whereby, a new permission target called INTERNAL_default appeared in the list of Permission Targets after upgrading Artifactory.                                                                                                                                                                                                                |
| INST-10787                                                                                                                | Installation                 | Medium   | Fixed an issue whereby the Artifactory Helm chart was misconfigured to read the `nodePort` value from `artifactory.nodePort` instead of the intended `artifactory.service.nodePort`, causing fixed `nodePort` settings to be ignored during deployments.                                                                                                       |
| INST-11384                                                                                                                | Installation                 | Medium   | Fixed an issue whereby the `docker-compose-all.yaml` template for Artifactory did not expose Nginx ports (80 and 443) by default, preventing customer access to the Nginx container.                                                                                                                                                                           |
| INST-9279                                                                                                                 | Installation                 | Medium   | Fixed an issue where the **serviceName** in the **artifactory-statefulset.yaml** and the **artifactory-service.yaml** files were not identical, causing DNS resolution failures.                                                                                                                                                                               |
| RTDEV-59631                                                                                                               | Packages                     | Medium   | Fixed an issue whereby Docker referrers were not passed to the federated repository.                                                                                                                                                                                                                                                                           |
| RTDEV-55520                                                                                                               | Packages                     | High     | Fixed an issue whereby after resolving the release or InRelease file using a Debian virtual repository, the merged release file didn't include components from all repositories aggregated in the virtual repository.                                                                                                                                          |
| RTDEV-56028                                                                                                               | Packages                     | Medium   | Fixed an issue whereby the npm search on an npm repository with more than 20 artifacts did not provide the correct latest version.                                                                                                                                                                                                                             |
| RTDEV-56101                                                                                                               | Packages                     | Medium   | Fixed an issue whereby corrupted cache from an npm remote repository was breaking the resolution of packages.                                                                                                                                                                                                                                                  |
| RTDEV-56651                                                                                                               | Packages                     | Medium   | Fixed an issue whereby an empty string in the **noarch** element in the Conda **repodata.json** metadata file caused a failure when downloading artifacts from a Conda repository with a pixi client.                                                                                                                                                          |
| RTDEV-57071                                                                                                               | Packages                     | Medium   | Fixed an issue whereby the **nuget search** command returned an empty response when searching for packages in a NuGet virtual repository that contained a remote GitHub packages repository.                                                                                                                                                                   |
| RTDEV-57187                                                                                                               | Packages                     | Medium   | Fixed an issue whereby a 500 error was received when executing the Get RubyGem Version List REST API on a virtual repository.                                                                                                                                                                                                                                  |
| RTDEV-57309                                                                                                               | Packages                     | Medium   | Fixed an issue whereby it was not possible to delete an improper **list.manifest.json** in a Docker repository.                                                                                                                                                                                                                                                |
| RTDEV-57815                                                                                                               | Packages                     | Medium   | Fixed an issue in the max unique tags Docker cleanup feature where tags were removed out of order.                                                                                                                                                                                                                                                             |
| RTDEV-57859                                                                                                               | Packages                     | Medium   | Fixed an issue whereby, the SAX parser failed when parsing filtered XML resources.                                                                                                                                                                                                                                                                             |
| RTDEV-58355                                                                                                               | Packages                     | High     | Fixed an issue whereby the upload of large files failed with Azure cloud providers.                                                                                                                                                                                                                                                                            |
| RTDEV-58640                                                                                                               | Packages                     | Medium   | Fixed an issue whereby some versions of certain composer packages were not listed or downloadable when using a composer remote repository configured with default settings.                                                                                                                                                                                    |
| RTFE-3107                                                                                                                 | Packages                     | Medium   | Fixed an issue whereby the option to “Enable Indexing in Xray” appeared in the configuration of Machine Learning repositories.                                                                                                                                                                                                                                 |
| <Anchor label="RTFACT-31181" target="_blank" href="https://jfrog.atlassian.net/browse/RTFACT-31181">RTFACT-31181</Anchor> | Packages                     | Low      | Fixed an issue whereby an exclamation mark incorrectly appeared in the code snippet for manually setting credentials in the Set Me Up procedure for OCI repositories.                                                                                                                                                                                          |
| JA-17278                                                                                                                  | Platform Management          | Medium   | Fixed the issue whereby a global role created at the Platform level was unexpectedly automatically appearing under project roles.                                                                                                                                                                                                                              |
| JA-17177                                                                                                                  | Projects                     | High     | Fixed an issue whereby project-level access tokens were circumventing the Read-Only restriction in a shared repository.                                                                                                                                                                                                                                        |
| RTDEV-45715                                                                                                               | Release Lifecycle Management | Medium   | Fixed an issue whereby a build rename failed (because the build was not found in the defined project), but the operation was still reported as successful. After the fix, an error message is returned if a build with the specified name is not found in the defined project.                                                                                 |
| RTDEV-54817                                                                                                               | Release Lifecycle Management | Medium   | Fixed an issue that prevented webhook notifications from being triggered for each artifact in a Release Bundle v2 promotion. After the fix, users who have configured artifact copy/move webhook notifications (and include `<project-key>-release-bundles-v2` repositories) will receive notifications about each artifact when Release Bundles are promoted. |
| RTDEV-55410                                                                                                               | Release Lifecycle Management | Medium   | Fixed an issue whereby when trying to append an artifact to an empty build via the Build Append REST API, an error was encountered.                                                                                                                                                                                                                            |
| RTDEV-56117                                                                                                               | Release Lifecycle Management | Medium   | Fixed an issue that caused the platform UI to show an inaccurate number of items inside the packages contained in a Release Bundle.                                                                                                                                                                                                                            |
| RTDEV-56347                                                                                                               | Release Lifecycle Management | Medium   | Fixed an issue whereby only the latest piece of evidence was preserved when promoting a release bundle with Move.                                                                                                                                                                                                                                              |
| RTDEV-57055                                                                                                               | Release Lifecycle Management | Medium   | Fixed an issue that caused the build cleanup procedure to fail after the associated project was deleted.                                                                                                                                                                                                                                                       |
| RTDEV-59330                                                                                                               | Release Lifecycle Management | High     | Fixed an issue that caused artifacts to be deleted when a Release Bundle was promoted using the `move` option to the environment in which it already resides.                                                                                                                                                                                                  |
| <Anchor label="RTFACT-31184" target="_blank" href="https://jfrog.atlassian.net/browse/RTFACT-31184">RTFACT-31184</Anchor> | Release Lifecycle Management | High     | Fixed an issue that prevented the creation of a Release Bundle v2 version from a build containing multiple images that share a layer.                                                                                                                                                                                                                          |
| JA-16404                                                                                                                  | Repositories                 | Medium   | Fixed an issue related to Generic Repository Set-Me-Up whereby, when creating an identity token, the JFrog Platform did not include all required scopes.                                                                                                                                                                                                       |
| RTDEV-60496                                                                                                               | Repositories                 | High     | Fixed an issue whereby the **.jfrog** system folder could not be deleted from local repositories or remote caches.                                                                                                                                                                                                                                             |
| RTDEV-55094                                                                                                               | Repositories                 | Low      | Fixed an issue whereby, when a remote repository pointed to a blocked URL, the **Disable Artifact Resolution in Repository** setting could not be disabled even though the update request returned a 200 status code.                                                                                                                                          |
| RTDEV-55756                                                                                                               | Repositories                 | Medium   | Fixed an issue where, after encountering a connection error with a remote repository, Artifactory prematurely reset the repository's offline status before completing an online check.                                                                                                                                                                         |
| <Anchor label="RTFACT-30732" target="_blank" href="https://jfrog.atlassian.net/browse/RTFACT-30732">RTFACT-30732</Anchor> | Repositories                 | Medium   | Fixed an issue whereby, when setting members in a virtual repository the order in the YAML configuration file was not maintained.                                                                                                                                                                                                                              |
| <Anchor label="RTFACT-31100" target="_blank" href="https://jfrog.atlassian.net/browse/RTFACT-31100">RTFACT-31100</Anchor> | Repositories                 | Low      | Fixed an issue whereby, when trying to create a repository using the Create Repository Rest API without an "include pattern" in the input JSON, the repository was created with an empty string for the "include pattern" field.                                                                                                                               |
| <Anchor label="RTFACT-31120" target="_blank" href="https://jfrog.atlassian.net/browse/RTFACT-31120">RTFACT-31120</Anchor> | Repositories                 | Medium   | Fixed an issue whereby when a Smart-Remote repository on Edge was pointing to another Artifactory instance and had artifacts in the cache, if the Main instance was up but had returned an unexpected error code, artifacts could not be resolved even if they were in the cache.                                                                              |
| RTDEV-55932                                                                                                               | Storage                      | Low      | Fixed an issue whereby the storage summary graph that appears under Monitoring > Storage showed incorrect usage.                                                                                                                                                                                                                                               |
| JA-17192                                                                                                                  | User Interface               | Low      | Fixed an issue whereby the **Disable Internal Password Login** setting was not functioning correctly when configured globally.                                                                                                                                                                                                                                 |
| JA-17258                                                                                                                  | User Interface               | High     | Fixed an issue whereby, when creating a group via the JFrog Platform WebUI, the **Read Policy** role was not displayed.                                                                                                                                                                                                                                        |
| JFUI-18147                                                                                                                | User Interface               | Medium   | Fixed an issue whereby after clicking a URL to a specific package and needing to log in, users were directed to the general package page instead of the package referred to in the URL.                                                                                                                                                                        |
| RTFE-3191                                                                                                                 | User Interface               | High     | Fixed an issue whereby the Trash Can could not re-enabled after disabling it via the User Interface.                                                                                                                                                                                                                                                           |
| TOPO-592                                                                                                                  | User Interface (UI)          | High     | Fixed an issue related to monitoring whereby, under certain circumstances, the Service Status page in the JFrog Platform WebUI displayed inaccurate uptime information for services.                                                                                                                                                                           |
| JA-17040                                                                                                                  | User Management              | Medium   | Fixed a issue with synchronization in Access Federation for groups containing the 'anonymous' user, as the user's membership wasn't getting replicated.                                                                                                                                                                                                        |
| JA-17058                                                                                                                  | User Management              | Medium   | Fixed an issue whereby when creating a user scoped token in the UI, then changes it during creation to a group scoped token, the token is created including the username previously selected (in user scoped token UI) instead of the logged in user's username required for group scoped token.                                                               |
| RTDEV-57047                                                                                                               | User Management              | Medium   | Fixed an issue whereby an access project scoped token with the "Viewer" role allowed artifact deployment.                                                                                                                                                                                                                                                      |
