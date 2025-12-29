---
title: jfrog test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
# What is JFrog Artifactory?

JFrog Artifactory is the single solution for housing and managing all the software artifacts, AI/ML models, binaries, packages, files, containers, components, and releases used in and generated across your organization’s software supply chain. Artifactory serves as your central hub for DevOps and developers - integrating with your tools and processes to improve automation, capture attestation, ensure release integrity, and provide unrivaled visibility across your development processes.

For more information, see how Artifactory operates as a proxy for Packages in [Working with Package Management](doc:working-with-package-management).

***

# Set up Artifactory

Before starting you need to set up Artifactory. If you haven't done this yet, see [Set up Artifactory ](/setup/docs/get-started).

***

# Connect your package manager or IDE

Once you've set up Artifactory as your universal artifact repository, you need to take three primary steps to begin using Artifactory as your artifact repository:

<Image align="center" border={false} src="https://files.readme.io/79d327945e4779faa933555cf125b0f53dfdabc0e3848c5ad3fe425420b60047-three-steps.png" />

* **Create an Artifactory Repository**  
  Create a local repository to share binaries with your colleagues, a virtual repository to proxy requests from external Artifact Registries and Repositories, or virtual to combine the two. For more information see [Repository Management Overview](doc:repository-management-overview). Note you need Admin permissions to create repositories

* **Update your Package Manager Client**  
  Every developer in your organization needs to update their package manager client on their workstation to point to Artifactory. Instructions are different for every repository and registry and every package manager.
  * **Connect to your registry**: For more information see [Connect your Package Manager or IDE to Artifactory](doc:connect-your-package-manager-to-artifactory) and follow the instructions for the specific registry or repository (e.g. Docker, Maven)
  * **Copy commands for Configuration**: via the set me up functionality to use for configuring your package manager. For information see [Use Artifactory Set Me Up for Configuring Package Manager Clients](doc:use-artifactory-set-me-up-for-configuring-package-manager-clients)

* **Push and Pull Images**  
  Once you've created a repository and updated your package manager, you can begin to work. For more information see [Upload and Download Packages using Artifactory](doc:upload-and-download-packages-using-artifactory).

For more information on working with Artifactory as your package manager, see [Working with Package Management](doc:working-with-package-management).

***

# Learn about Artifactory

<Cards columns={3}>
  <Card title="Get Started with the JFrog Trial" href="/setup/docs/get-started" target="_blank">
    Not yet started? Register for the JFrog Trial and begin to get your hands dirty.
  </Card>

  <Card title="See Supported Package Types" href="/artifactory/docs/supported-package-types">
    See the list of the more than 50 registries and repositories supported by JFrog Artifactory.
  </Card>

  <Card title="Read Package Management Use Cases" href="/artifactory/docs/package-and-repositories-use-cases">
    Learn about two central use cases for artifactory. Package caching and proxying, and managing machine learning operations.
  </Card>

  <Card title="Work with JFrog Repositories" href="/artifactory/docs/repository-management" target="_blank">
    Learn about the different types of repositories in JFrog, how to create and configure them and understanding their usage.
  </Card>

  <Card title="Learn about Package Management" href="/artifactory/docs//working-with-package-management">
    See how artifactory operates as your central package and artifact repository. Learn how to efficiently search and find your artifacts.
  </Card>

  <Card title="Distribute Packages" href="/artifactory/docs/jfrog-distribution">
    Use artifactory to distribute artifacts and release bundles across edges.
  </Card>
</Cards>
