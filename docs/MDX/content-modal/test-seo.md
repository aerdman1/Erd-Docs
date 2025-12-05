---
title: Test SEO
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---


<Table>
  <tbody>
    <tr>
      <td>
        Bash
      </td>
      <td>
        `write_output <resource> <key value pair>... [--overwrite]`
      </td>
    </tr>
    <tr>
      <td>
        PowerShell
      </td>
      <td>
        `write_output <resource> <key value pair>... [-overwrite]`
      </td>
    </tr>
  </tbody>
</Table>



* `resource` is the resource to update
* `key value pair` is a single string with a key and a value, separated by an “=”. Multiple of these strings can be supplied as input. A value with spaces should be surrounded by quotes.


<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        Powershell
      </th>
      <th>
        Option Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **--overwrite**
      </td>
      <td>
        **-overwrite**
      </td>
      <td>
        If supplied, all key value pairs will be replaced.
      </td>
    </tr>
  </tbody>
</Table>



`write_output myImageimageTag=master sha=$commitSha description=\"hello world\"`

The newly attached properties can be accessed as environment variables of the form `res_{Resource Name}_{Key Name}`.

For example, the above created properties can be accessed as these environment variables:

```
$ printenv res_myImage_master
master
$ printenv res_myImage_sha
d6cd1e2bd19e03a81132a23b2025920577f84e37
$ printenv res_myImage_description
"hello world"
```

## Caching

Caching helps you speed up execution of your steps by preserving and restoring packages and dependencies between runs of a step. In this way, you can reduce build times by avoiding repeating the installation or loading of large dependencies.

The following Caching functions are available for Pipelines:

* [add\_cache\_files](/docs/add_cache_files "add_cache_files")
* [restore\_cache\_files](/docs/restore_cache_files "restore_cache_files")

### add_cache_files

**Description**

Copies files given as input to later be uploaded if file storage is available.

For more information about using this utility function, see [Caching Step Runtimes](/docs/caching-step-runtimes "Caching Step Runtimes").

**Usage**

`add_cache_files <file or directory> <name>`

* `file or directory` is a file or directory to store in the cache
* `name` is a name to give the stored file or directory (without spaces)

`add_cache_files cachefile.txt my_file`

`add_cache_files directory/subdirectory my_directory`

### restore_cache_files

**Description**

Copies stored cache (if file storage is available) to the specified location. No error will occur if nothing is available for `<name>` in the cache.

Use this utility function when you want to make use of files generated from the first step in the second step, which runs only after first step finishes.

**Usage**

`restore_cache_files <name> <path>`

* `name` is the name the file or driectory to be restored was given when cached.
* `path` is a path at which to place the file or directory.

`restore_cache_files my_file cachefile.txt`

`restore_cache_files my_directory directory/subdirectory`

## Run State Management

The following Run State Management functions are available for Pipelines:

* [add\_run\_variables](/docs/add_run_variables "add_run_variables")
* [export\_run\_variables](/docs/export_run_variables "export_run_variables")
* [add\_run\_files](/docs/add_run_files "add_run_files")
* [restore\_run\_files](/docs/restore_run_files "restore_run_files")
* [update\_run\_description](/docs/update_run_description "update_run_description")
* [restore\_run\_files](/docs/restore_run_files "restore_run_files")

### add_run_variables

**Description**

Allows you to add environment variables that will be available in the following steps of the run.

If the following variables are set, they will be used:

* `JFROG_CLI_BUILD_NAME`: If set, the pipeline uses this value instead of the default pipeline name for the build info collected.
* `JFROG_CLI_BUILD_NUMBER`: If set, the pipeline uses this value instead of the default run number for the build info collected.
* `USE_LOCAL_JFROG_CLI`: If set as `true`, the local JFrog CLI on the host or in the image (depending on `runtime` configuration) is used instead of the version packaged with JFrog Pipelines. This is not recommended and native steps may not be able to run with the local JFrog CLI version.

**Usage**

`add_run_variables <key value pair>...`

* `key value pair` is a single string with a key and a value, separated by an “=”. Multiple of these strings can be supplied as input. Each value will be exported as an environment variable at the time this command is used and automatically in any later steps within the run.

add\_run\_variables imageTag="master"

### export_run_variables

**Description**

Sources the file containing the run variables. This will be done automatically, but may also be used to “reset” the environment variables in the current step.

**Usage**

`export_run_variables`

`export_run_variables`

### add_run_files

**Description**

Copies files given as input into the run state for use in later steps in the run, if file storage is available.

Use this utility function when you want to make use of files generated from the first step in the second step, which runs only after first step finishes.

**Usage**

`add_run_files <file or directory> <name>`

`file or directory` is a file or directory to store in the run state

`name` is a name to give the stored file or directory (without spaces). This cannot be run.env.

`add_run_files cachefile.txt my_file`

`add_run_files directory/subdirectory my_directory`

`add_run_files directory/*/subdirectory my_directory`

### set_run_name

**Description**

Provide a unique, dynamic name for a run, which will be shown in the UI. This is useful for providing more context about a run. Unlike run description, run name is unique for a run.

In the UI, run name appears in the Run View:

![180146976.png](../../../image/uuid-a36cb151-8373-d7a4-d038-b5c7bc944acc.png)

Run name appears also appears in Pipeline of Pipelines view and Active Board view:

![180146977.png](../../../image/uuid-020af9af-ca92-fab3-8e3d-cd638921348a.png)

**Usage**



<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        `set_run_name "1.0.1"`
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        PowerShell
      </td>
      <td>
        `set_run_name "1.0.1"`
      </td>
    </tr>
  </tbody>
</Table>



`set_run_name "1.0.1"`

`set_run_name "1.0.1"`

Full YAML Example

```
name: UpdateRunDescription
steps:
        - name: update_l
          type: Bash
          execution:
                onStart:
                        - set_run_name "1.0.1"
        - name: update_2
          type: Bash
          configuration:
                inputSteps:
                        - name: update_l
          execution:
                onStart:
                        - msg="Run description updated from step $step_id"
                        - update_run_description "$msg"
```

### update_run_description

**Description**

Provide dynamic description for a run, which will be shown in the UI. This is useful for providing more context about a run. Every step in a pipeline can include a run description.

**Usage**



<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        `update_run_description "description"`
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        PowerShell
      </td>
      <td>
        `update_run_description "description"`
      </td>
    </tr>
  </tbody>
</Table>



`update_run_description "$msg"`

`update_run_description "$msg"`

Full YAML Example

```
name: UpdateRunDescription
steps:
        - name: update_l
          type: Bash
          execution:
                onStart:
                        - msg="Run description updated from step $step_id"
                        - update_run_description "$msg"
        - name: update_2
          type: Bash
          configuration:
                inputSteps:
                        - name: update_l
          execution:
                onStart:
                        - msg="Run description updated from step $step_id"
                        - update_run_description "$msg"
```

### restore_run_files

**Description**

Copies files stored in the run state (if file storage is available) to the specified location. No error will occur if nothing is available for `<name>` in the run state.

Use this utility function when you want to make use of files generated from the first step in the second step, which runs only after first step finishes.

**Usage**

`restore_run_files <name> <path>`

* `path` is the name the files to be restored were given when added to the run state.
* `file or directory` is a path at which to place the file or files.

`restore_run_files my_file cachefile.txt`

`restore_run_files my_directory directory/subdirectory`

## Affinity Group State Management

The following Affinity Group State Management functions are available for Pipelines:

* [add\_affinity\_group\_files](/docs/add_affinity_group_files "add_affinity_group_files")
* [restore\_affinity\_group\_files](/docs/restore_affinity_group_files "restore_affinity_group_files")

### add_affinity_group_files

**Description**

Copies files or directories given as input into the affinity group workspace for use in later steps in the affinity group. Files or directories may be specified using wildcards (*) or as multiple input parameters preceding the name under which the files will be stored.

**Usage**

`add_affinity_group_files <file or directory> <name>`

`file or directory` is a file or directory to store in the run state.

`name` is a name to give the stored file or directory (without spaces).

`add_affinity_group_files cachefile.txt my_file`

`add_affinity_group_files myDirectory myOtherDirectory/subdirectory my_directories`

`add_affinity_group_files myDirectory/*.txt my_text_files`

`add_affinity_group_files ../adjacentDirectory my_adjacent_directory`

### restore_affinity_group_files

**Description**

Copies files stored in the affinity group workspace by `add_affinity_group_files` to the specified location. The restore behavior differs from the other state restore functions to better handle wildcard patterns with a variable number of matching files or directories. With `restore_affinity_group_files`, the relative path specified in the `add_affinity_group_files` function will be preserved (excluding any traversal to parent directories) and the path specified should be the base for that relative path. The following examples are to symmetrically restore the files saved in the examples above for `add_affinity_group_files.` No error will occur if no files were saved for `<name>`.

**Usage**

`restore_affinity_group_files <name> <path>`

* `name` is the name the files to be restored were given when storing the files with `add_affinity_group_files`.
* `path` is a path at which to place the file or files.

`restore_affinity_group_files my_file .`

`restore_affinity_group_files my_directories .`

`restore_affinity_group_files my_text_files .`

`restore_affinity_group_files my_adjacent_directory ..`

## Pipeline State Management

The following Pipeline State Management functions are available for Pipelines:

* [add\_pipeline\_variables](/docs/add_pipeline_variables "add_pipeline_variables")
* [export\_pipeline\_variables](/docs/export_pipeline_variables "export_pipeline_variables")
* [add\_pipeline\_files](/docs/add_pipeline_files "add_pipeline_files")
* [restore\_pipeline\_files](/docs/restore_pipeline_files "restore_pipeline_files")

### add_pipeline_variables

**Description**

Allows you to add environment variables that will be available in the following steps of the run and in future runs. These variables may be overridden by another variable with the same key added to the current run.

If the following variables are set, they will be used:

* `JFROG_CLI_BUILD_NAME`: If set, the pipeline uses this value instead of the default pipeline name for the build info collected.
* `JFROG_CLI_BUILD_NUMBER`: If set, the pipeline uses this value instead of the default run number for the build info collected.
* `USE_LOCAL_JFROG_CLI`: If set as `true`, the local JFrog CLI on the host or in the image (depending on `runtime` configuration) is used instead of the version packaged with JFrog Pipelines. This is not recommended and native steps may not be able to run with the local JFrog CLI version.

**Usage**

`add_pipeline_variables <key value pair>...`

* `key value pair` is a single string with a key and a value, separated by an “=”. Multiple of these strings can be supplied as input. Each value will be exported as an environment variable at the time this command is used and automatically in any steps that start after this run is complete.

`add_pipeline_variables imageTag="master"`

`add_pipeline_variables imageName="myimage" imageTag="master"`

### export_pipeline_variables

**Description**

Sources the file containing the pipeline variables. This will be done automatically, but may also be used to “reset” the environment variables in the current step.

**Usage**

`export_pipeline_variables`

`export_pipeline_variables`

### add_pipeline_files

**Description**

Copies files given as input into the pipeline state for use in later steps in the run and future runs, if file storage is available.

Use this utility function when you want to make use of files generated from the first step in the second step, which runs only after first step finishes.

**Usage**

`add_pipeline_files <file or directory> <name>`

* `file or directory` is a file or directory to store in the pipeline state.
* `name` is a name to give the stored file or directory (without spaces). This cannot be pipeline.env.

`add_pipeline_files cachefile.txt my_file`

`add_pipeline_files directory/subdirectory my_directory`

### restore_pipeline_files

**Description**

Copies files stored in the pipeline state (if file storage is available) to the specified location. No error will occur if nothing is available for `<name>` in the run state.

Use this utility function when you want to make use of files generated from the first step in the second step, which runs only after first step finishes.

**Usage**

`restore_pipeline_files <name> <path>`

* `name` is the name the file to be restored was given when added to the pipeline state.
* `path` is a path at which to place the file or files.

`restore_pipeline_files my_file cachefile.txt`

`restore_pipeline_files my_directory directory/subdirectory`

## Step Properties

The following Step Properties are available for Pipelines:

* [find\_resource\_variable](/docs/find_resource_variable "find_resource_variable")
* [get\_integration\_name](/docs/get_integration_name "get_integration_name")
* [get\_resource\_name](/docs/get_resource_name "get_resource_name")
* [get\_resource\_names](/docs/get_resource_names "get_resource_names")
* [get\_affinity\_group\_step\_names](/docs/get_affinity_group_step_names "get_affinity_group_step_names")
* [find\_step\_configuration\_value](/docs/find_step_configuration_value "find_step_configuration_value")
* [end\_step](/docs/end_step "end_step")

### find_resource_variable

**Description**

Retrieves the value of the named property of a resource.

**Usage**

`find_resource_variable <resourceName> <propertyName>`

* `resourceName` is the name of the resource.
* `propertyName` is the name of the resource property whose value to retrieve.

`find_resource_variable myGitHub commitSha`

`find_resource_variable myImage imageTag`

### get_integration_name

**Description**

Retrieves the name of the first integration found of the type specified. Available to extension steps to get the name of the first input integration of a particular type.

**Usage**

`get_integration_name --type <integration type>`

* `integration type` is the name of an [Pipelines Integration type](/docs/pipelines-integrations "Pipelines Integrations")

`get_integration_name --type Slack`

`get_integration_name --type "Docker Registry"`

### get_resource_name

**Description**

Retrieves the name of the first resource found of the type specified in `inputResources` or `outputResources`. Available to extension steps to get the name of the first input or output resource of a particular type.

**Usage**

get\_resource\_name --type `<resource type>` --operation `<IN | OUT>` --syntax-version `<semver>`

* `resource type` is the name of a [Pipelines Resource type](/docs/pipelines-resources "Pipelines Resources")
* `IN | OUT` selects whether the resource is named in `inputResources` or `outputResources`
* `semver` is the semantic version number of the resource's syntax version

`get_resource_name --type GitRepo --operation IN`

get\_resource\_name --type BuildInfo --operation OUT

`get_resource_name --type GitRepo --operation IN --syntax-version 1.5.0`

### get_resource_names

**Description**

Retrieves an array of names of the type specified in `inputResources` or `outputResources`. Available to extension steps to get the names of input or output resource of a particular type.

**Usage**

get\_resource\_names --type `<resource type>` --operation `<IN | OUT>` --syntax-version `<semver>`

* `resource type` is the name of a [Pipelines Resource type](/docs/pipelines-resources "Pipelines Resources")
* `IN | OUT` selects whether the resource is named in `inputResources` or `outputResources`
* `semver` is the semantic version number of the resource's syntax version
* In PowerShell, a native PowerShell array is returned. In Bash, a JSON array is returned that can be handled with jq.

`get_resource_names --type GitRepo --operation IN`

get\_resource\_names --type BuildInfo --operation OUT

`get_resource_names --type GitRepo --operation IN --syntax-version 1.5.0`

### get_affinity_group_step_names

**Description**

Retrieves a JSON array of names of steps of the type specified in the current affinity group.

**Usage**

`get_affinity_group_step_names [--type <step type>]  [--syntax-version <semver>] [--namespace <namespace>]find_step_configuration_value <propertyName>`

* `type` is used to specify the type of the steps to be found. If not specified, steps of all types will be returned.
* `syntax-version` is used to specify the type of the steps to be found. If not specified, steps of all types will be returned.
* `namespacetype` is used with extension steps to specify the namespace of the steps to be found.

`get_affinity_group_step_namesfind_step_configuration_value forceXrayScan`

`get_affinity_group_step_names --type GitRepo`

`get_affinity_group_step_names --type MyExtension --syntax-version 1.5.0`

`get_affinity_group_step_names --type MyExtension --namespace myNamespace --syntax-version 1.5.0`

### find_step_configuration_value

**Description**

Retrieves the value of the `configuration` property for the currently executing step. If the property is a collection, the first value will be returned. Available to extension steps to get the value of a configuration.

**Usage**

`find_step_configuration_value <propertyName>`

* `propertyName` is the name of the step's configuration property whose value to retrieve

`find_step_configuration_value forceXrayScan`

### end_step

**Description**

Stops execution of the onStart or onExecute section and immediately continues to the onSuccess, onFailure, or onComplete section setting the specified status. If "success" is provided, the onSuccess and onComplete sections will be executed. For "failure," the onFailure and onComplete sections will be executed. And for "skipped," only the onComplete section. The end\_step utility function may only be called in the onStart and onExecute sections and the only statuses supported are success, failure, and skipped.

**Usage**



<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        `end_step [success|failure|skipped]`
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        PowerShell
      </td>
      <td>
        `end_step [success|failure|skipped]`
      </td>
    </tr>
  </tbody>
</Table>



`end_step success`

`end_step success`