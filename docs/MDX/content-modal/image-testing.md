---
title: image testing
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
There are several ways to view evidence in Artifactory:

* Select an artifact or build and view a table of evidence files (internal and external) associated with the artifact or build. From the table, you can download evidence files to your local system. For more information, see <Anchor label="View the Artifact Evidence Table" title="View the Artifact Evidence Table" href="/docs/view-the-artifact-evidence-table">View the Artifact Evidence Table</Anchor> and <Anchor label="View the Build Evidence Table" title="View the Build Evidence Table" href="/docs/view-the-build-evidence-table">View the Build Evidence Table</Anchor>.
* Select a Release Bundle v2 and view its content graph, which provides a graphical depiction of the evidence files associated with the Release Bundle and the builds and packages it contains. For more information, see <Anchor label="View Release Bundle v2 Evidence" title="View Release Bundle v2 Evidence" href="/docs/view-release-bundle-v2-evidence">View Release Bundle v2 Evidence</Anchor>.
* The evidence graph and the evidence table in the artifact tree can be used to view the <Anchor label="predicate" title="Evidence Predicate" href="/docs/evidence-predicate">predicate</Anchor>, which contains the actual contents of the evidence file. For more information, see <Anchor label="View the Evidence Predicate" title="View the Evidence Predicate" href="/docs/view-the-evidence-predicate">View the Evidence Predicate</Anchor>.
* You can view a list of evidence-related events associated with a Release Bundle v2 version (such as promotion to an environment) in the version <Anchor label="timeline" title="Use the Release Bundle Version Timeline" href="/docs/use-the-release-bundle-version-timeline">timeline</Anchor>.

## View the Artifact Evidence Table

When you select a local repository, virtual repository, or Release Bundle v2 from the [repository tree](/artifactory/docs/browsing-artifacts#UUID-3d3902be-c455-0fd0-0393-326a7e469be3), use the **Evidence** tab to view a list of external evidence files associated with the Release Bundle and its contents. You can download these files to your local server.

**To view the artifact evidence table**:

1. In the **Application** module, select **Artifactory > Artifacts**.

2. Select an artifact from the tree. Details about the artifact are displayed in a series of tabs in the pane to the right of the tree. For more information, see [Artifact Information](/artifactory/docs/artifact-information#UUID-f79e8dec-38cc-863d-b72a-c638ed32d9f5).

3. Click the **Evidence** tab to display the evidence table.

   <Image align="center" alt="artifact-evidence_provider-logo.png" border={false} width="60% " src="https://files.readme.io/a15e4f179303325defa443c86fcf808296df2b7582baa84f484cc6e72fb5442e-uuid-c4e0a2f3-b4ad-31f3-c772-1a9960aed332.png" />

   The table lists all external evidence files related to the selected artifact.

<Table>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Verified
      </td>

      <td>
        A blue checkmark icon ![](https://files.readme.io/206e04b338f9a2f215c45b8a329bd0ef288bea60788a57f497d5b35365397b1b-uuid-3bd5e91a-89db-eb21-c3d1-09d11a1cc19e.png) indicates the evidence has been verified using the public key created for this purpose. For more information, see <Anchor label="Create a Key Pair for Evidence" title="Create a Key Pair for Evidence" href="/docs/create-a-key-pair-for-evidence">Create a Key Pair for Evidence</Anchor>.
      </td>
    </tr>

    <tr>
      <td>
        Evidence Type
      </td>

      <td>
        The type of evidence contained in the file, for example, vulnerability scan, code scan, test result, or commit. An icon representing the evidence provider is displayed next to the name.
      </td>
    </tr>

    <tr>
      <td>
        Category
      </td>

      <td>
        The category under which the evidence file is classified, as determined by the predicate type. Categories include:

        * **Audit** (for example, approvals)
        * **Quality** (for example, test results)
        * **Security** (for example, evidence related to SAST and code scans)
        * **Workflow** (for example, internal evidence relating to the promotion and distribution of Release Bundles)
        * **Custom** (other types of external evidence attached by the user)
      </td>
    </tr>

    <tr>
      <td>
        Time
      </td>

      <td>
        The timestamp that indicates when the evidence file was created.
      </td>
    </tr>

    <tr>
      <td>
        Created By
      </td>

      <td>
        The name of the user who created the evidence file.
      </td>
    </tr>

    <tr>
      <td>
        Actions menu
      </td>

      <td>
        Click the icon ![](https://files.readme.io/562b2af49cb69acd8de39c4d2ca0d310a9e090a8b5cb737ae43a03cde58b8ca6-uuid-cb83d0cb-3b58-0261-f224-cadfa7e01a45.png) to select options for viewing and downloading evidence, as described below.
      </td>
    </tr>
  </tbody>
</Table>

#### View the Evidence File

To view the contents of the evidence file, select **View Evidence** from the actions menu.

<Image align="center" alt="Figma_evidence-contents-example.png" border={false} width="60% " src="https://files.readme.io/20c1ce1bab205697f2073501dfd557c82c600fb6623744e7eb959cba5f5d9ac5-uuid-0a6403af-6e76-cf1c-7133-2c315f29e3d0.png" />

<Callout icon="📘" theme="info">
  **Note**

  The platform UI can display a maximum of 3000 lines from the evidence file. If the file is larger than that, you are given the option to download the evidence instead. The maximum size of an evidence file supported by Artifactory is 16MB.
</Callout>

#### Download an Evidence File

To download an evidence file from the table, select **Download Evidence** from the actions menu.

## View the Package Evidence Table

When you select a package version from the Packages page, use the **Evidence** tab to view a list of external evidence files associated with the package. You can download these files to your local server.

**To view the package evidence table**:

1. In the **Application** module, select **Artifactory > Packages**.

2. Click the name of a package to display a table of package versions.

3. Click the relevant version to display the details of that version.

4. Click the **Evidence** tab.

5. Select a repository from the dropdown list above the table.

   <Image align="center" alt="packages-evidence_provider-logo.png" border={false} width="60% " src="https://files.readme.io/3ac40b9c35e69277fe187140a5fa6ecf39708a583666ed8c120f81ccea9b3299-uuid-a9b0e7dc-9d2c-a096-8409-de90ed54530b.png" />

   The table lists all external evidence files related to the package version in the selected repository.

<Table>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Verified
      </td>

      <td>
        A blue checkmark icon ![](https://files.readme.io/206e04b338f9a2f215c45b8a329bd0ef288bea60788a57f497d5b35365397b1b-uuid-3bd5e91a-89db-eb21-c3d1-09d11a1cc19e.png) indicates the evidence has been verified using the public key created for this purpose. For more information, see <Anchor label="Create a Key Pair for Evidence" title="Create a Key Pair for Evidence" href="/docs/create-a-key-pair-for-evidence">Create a Key Pair for Evidence</Anchor>.
      </td>
    </tr>

    <tr>
      <td>
        Evidence Type
      </td>

      <td>
        The type of evidence contained in the file, for example, vulnerability scan, code scan, test result, or commit. An icon representing the evidence provider is displayed next to the name.
      </td>
    </tr>

    <tr>
      <td>
        Category
      </td>

      <td>
        The category under which the evidence file is classified, as determined by the predicate type. Categories include:

        * **Audit** (for example, approvals)
        * **Quality** (for example, test results)
        * **Security** (for example, evidence related to SAST and code scans)
        * **Workflow** (for example, internal evidence relating to the promotion and distribution of Release Bundles)
        * **Custom** (other types of external evidence attached by the user)
      </td>
    </tr>

    <tr>
      <td>
        Time
      </td>

      <td>
        The timestamp that indicates when the evidence file was created.
      </td>
    </tr>

    <tr>
      <td>
        Created By
      </td>

      <td>
        The name of the user who created the evidence file.
      </td>
    </tr>

    <tr>
      <td>
        Actions menu
      </td>

      <td>
        Click the icon ![](https://files.readme.io/562b2af49cb69acd8de39c4d2ca0d310a9e090a8b5cb737ae43a03cde58b8ca6-uuid-cb83d0cb-3b58-0261-f224-cadfa7e01a45.png) to select options for viewing and downloading evidence, as described below.
      </td>
    </tr>
  </tbody>
</Table>

#### View the Evidence File

To view the contents of the evidence file, select **View Evidence** from the actions menu.

<Image align="center" alt="Figma_evidence-contents-example.png" border={false} width="60% " src="https://files.readme.io/20c1ce1bab205697f2073501dfd557c82c600fb6623744e7eb959cba5f5d9ac5-uuid-0a6403af-6e76-cf1c-7133-2c315f29e3d0.png" />

<Callout icon="📘" theme="info">
  **Note**

  The platform UI can display a maximum of 3000 lines from the evidence file. If the file is larger than that, you are given the option to download the evidence instead. The maximum size of an evidence file supported by Artifactory is 16MB.
</Callout>

#### Download an Evidence File

To download an evidence file from the table, select **Download Evidence** from the actions menu.

## View the Build Evidence Table

When you select a build version from the Builds page, use the **Evidence** tab to view a list of external evidence files associated with the build. You can download these files to your local server.

**To view the build evidence table**:

1. In the **Application** module, select **Artifactory > Builds**.

2. Click the name of a build to display a table of build versions.

3. Click the relevant build ID to display the details of that build version.

4. Click the **Evidence** tab to display the evidence table.

   <Image align="center" alt="build_evidence_table.png" border={false} width="60% " src="https://files.readme.io/3f4005e5a6964ea2a1af3208c538877a1742c9d636c7b3aed85a0bc8f00a58d0-uuid-dbc504c1-5f1e-a506-46d5-d9e6defbf9f6.png" />

   The table lists all external evidence files related to the selected artifact.

<Table>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Verified
      </td>

      <td>
        A blue checkmark icon ![](https://files.readme.io/206e04b338f9a2f215c45b8a329bd0ef288bea60788a57f497d5b35365397b1b-uuid-3bd5e91a-89db-eb21-c3d1-09d11a1cc19e.png) indicates the evidence has been verified using the public key created for this purpose. For more information, see <Anchor label="Create a Key Pair for Evidence" title="Create a Key Pair for Evidence" href="/docs/create-a-key-pair-for-evidence">Create a Key Pair for Evidence</Anchor>.
      </td>
    </tr>

    <tr>
      <td>
        Evidence Type
      </td>

      <td>
        The type of evidence contained in the file, for example, vulnerability scan, code scan, test result, or commit.
      </td>
    </tr>

    <tr>
      <td>
        Category
      </td>

      <td>
        The category under which the evidence file is classified, as determined by the predicate type. Categories include:

        * **Audit** (for example, approvals)
        * **Quality** (for example, test results)
        * **Security** (for example, evidence related to SAST and code scans)
        * **Workflow** (for example, internal evidence relating to the promotion and distribution of Release Bundles)
        * **Custom** (other types of external evidence attached by the user)
      </td>
    </tr>

    <tr>
      <td>
        Time
      </td>

      <td>
        The timestamp that indicates when the evidence file was created.
      </td>
    </tr>

    <tr>
      <td>
        Created By
      </td>

      <td>
        The name of the user who created the evidence file.
      </td>
    </tr>

    <tr>
      <td>
        Actions menu
      </td>

      <td>
        Click the icon ![](https://files.readme.io/562b2af49cb69acd8de39c4d2ca0d310a9e090a8b5cb737ae43a03cde58b8ca6-uuid-cb83d0cb-3b58-0261-f224-cadfa7e01a45.png) to select options for viewing and downloading evidence, as described below.
      </td>
    </tr>
  </tbody>
</Table>

#### View the Evidence File

To view the contents of the evidence file, select **View Evidence** from the actions menu.

<Image align="center" alt="Figma_evidence-contents-example.png" border={false} width="60% " src="https://files.readme.io/20c1ce1bab205697f2073501dfd557c82c600fb6623744e7eb959cba5f5d9ac5-uuid-0a6403af-6e76-cf1c-7133-2c315f29e3d0.png" />

<Callout icon="📘" theme="info">
  **Note**

  The platform UI can display a maximum of 3000 lines from the evidence file. If the file is larger than that, you are given the option to download the evidence instead. The maximum size of an evidence file supported by Artifactory is 16MB.
</Callout>

#### Download an Evidence File

To download an evidence file from the table, select **Download Evidence** from the actions menu.

## View Release Bundle v2 Evidence

When you select a specific Release Bundle v2 version in the platform UI, you can view the evidence associated with that version in two formats:

* In the Evidence table, as described in <Anchor label="View the Release Bundle Version Evidence Table" title="View the Release Bundle Version Evidence Table" href="/docs/view-the-release-bundle-version-evidence-table">View the Release Bundle Version Evidence Table</Anchor>.
* In the content graph, which contains a graphical representation of the elements that comprise the Release Bundle version and the connections between them, including all related evidence. For more information, see <Anchor label="View the Contents of a Release Bundle v2 Version in the Platform UI" title="View the Contents of a Release Bundle v2 Version in the Platform UI" href="/docs/view-the-contents-of-a-release-bundle-v2-version-in-the-platform-ui">View the Contents of a Release Bundle v2 Version in the Platform UI</Anchor>.

## View the Evidence Predicate

When viewing the <Anchor label="evidence graph" title="View Release Bundle v2 Evidence" href="/docs/view-release-bundle-v2-evidence">evidence graph</Anchor> for a Release Bundle v2 version, click the card for an evidence file to view its <Anchor label="predicate" title="Evidence Predicate" href="/docs/evidence-predicate">predicate</Anchor>, which contains the actual contents of the evidence.

All evidence is available in JSON format. Internal evidence generated by Artifactory (such as Release Bundle v2 promotion reports) and Xray (such as SBOMs and vulnerability reports) is also available in Markdown for easy readability. When both formats are available, the Markdown version (including the evidence provider logo) is shown in the **Content** tab and the JSON version is shown in the **Spec** tab.

<Callout icon="✅" theme="okay">
  **Tip**

  The predicate can also be viewed from the **Evidence** tab in the Artifact tree. For more information, see <Anchor label="View the Artifact Evidence Table" title="View the Artifact Evidence Table" href="/docs/view-the-artifact-evidence-table">View the Artifact Evidence Table</Anchor>.
</Callout>

Sample predicates of different types are shown below.

#### Release Bundle v2 Promotion Predicate

<Anchor label="Promoting" title="Promote a Release Bundle v2 Version in the Platform UI" href="/docs/promote-a-release-bundle-v2-version-in-the-platform-ui">Promoting</Anchor> a Release Bundle v2 version creates internal evidence about the event.

<Image align="center" alt="evidence_promotion-contents_spec.png" border={false} width="60% " src="https://files.readme.io/04c9628d3d0b0ebfbeb22aa378df6623eb2a37c2781136cc4498a17c5dbc8cb4-uuid-d47e6289-ebae-0067-3199-9b07d765659c.png" />

<Image align="center" alt="evidence_promotion-contents_markdown_JFroglogo.png" border={false} width="60% " src="https://files.readme.io/1e7f77402bc932e764f6c8adee9e15482079ddfe0791b3253ed193eecea4fe64-uuid-8c0440e7-0ea0-fffb-84fe-781ce2c981ca.png" />

#### Release Bundle v2 Distribution Predicate

<Anchor label="Distributing" title="Distribute Release Bundles (v2)" href="/docs/distribute-release-bundles-v2">Distributing</Anchor> a Release Bundle v2 version to a target (such as an Edge node) creates internal evidence about the event.

<Image align="center" alt="evidence_distribution-predicate-example.png" border={false} width="60% " src="https://files.readme.io/be0888fe9dbaaf7f2646bedaf7c6a3e8631439bb8029c1545f2ee50c09599224-uuid-d23f4661-0be6-ffd5-7004-b45413455a5c.png" />

#### Xray Scan Results

The following is an example of vulnerability report evidence generated by Xray in Markdown format.

<Image align="center" alt="evidence_cyclonedx_content-jfroglogo.png" border={false} width="60% " src="https://files.readme.io/c4e8c49355a8b845aa3b8f80536b4c913cdc38f24a89b42fe77a8452a1d3d46f-uuid-624f4b76-5483-c689-dbe5-6829fc9c2af2.png" />

#### Test Results

Using the <Anchor label="Create Evidence CLI" target="_blank" href="https://docs.jfrog-applications.jfrog.io/jfrog-applications/jfrog-cli/binaries-management-with-jfrog-artifactory/evidence-service">Create Evidence CLI</Anchor>, you can attach external evidence, such as test results performed outside of Artifactory.

<Image align="center" alt="test-results_spec-example.png" border={false} width="60% " src="https://files.readme.io/6d3da351027cb0a4826e41e95c3804c07215d2ed7956d36690db255c56e00164-uuid-d7fb88c8-09df-4f6d-7961-d4f1eca55b8e.png" />

<Callout icon="✅" theme="okay">
  **Tip**

  Click the down arrow icon to download the evidence file to your local computer.
</Callout>

#### Evidence from an External Provider

Evidence uploaded from external providers are displayed with the provider logo, as shown in the example below.

<Image align="center" alt="Service-Now_evidence_code-review.png" border={false} width="60% " src="https://files.readme.io/c0f393a6c8ca7bc62368040a32e3df27c2f5f9468a5e9b814d038b22be933faa-uuid-b5119756-3f98-f40e-94cd-1c0cb4ebb8f9.png" />
