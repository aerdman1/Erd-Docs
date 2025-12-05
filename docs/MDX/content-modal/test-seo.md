---
title: Test SEO
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---



Creates a NewRelic deployment through a [NewRelic Integration](/docs/newrelic-integration "NewRelic Integration"). Not supported in PowerShell.



<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        Option Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **--type**
      </td>
      <td>
        the type of object to be posted. At the moment, only “deployment” is supported
      </td>
    </tr>
    <tr>
      <td>
        **--description**
      </td>
      <td>
        description of the deployment
      </td>
    </tr>
    <tr>
      <td>
        **--username**
      </td>
      <td>
        the user recording the deployment. Defaults to “JFrog Pipelines”
      </td>
    </tr>
    <tr>
      <td>
        **--changelog**
      </td>
      <td>
        the changelog value to use in the deployment
      </td>
    </tr>
    <tr>
      <td>
        **--revision**
      </td>
      <td>
        the deployment revision (required)
      </td>
    </tr>
    <tr>
      <td>
        **--appId**
      </td>
      <td>
        the ID of the app being deployed. If not provided, --appName must be present
      </td>
    </tr>
    <tr>
      <td>
        **--appName**
      </td>
      <td>
        the name of the app being deployed. If not provided, --appId must be present
      </td>
    </tr>
    <tr>
      <td>
        **--payload**
      </td>
      <td>
        path to a valid JSON file that contains a payload to use to POST the NewRelic deployment
      </td>
    </tr>
  </tbody>
</Table>



Sends an event through a [PagerDuty Events Integration](/docs/pagerduty-events-integration "PagerDuty Events Integration").



<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        PowerShell
      </th>
      <th>
        Option Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **--text**
      </td>
      <td>
        **-text**
      </td>
      <td>
        The main text to display in the event on PagerDuty.
      </td>
    </tr>
  </tbody>
</Table>



Slack

Sends a message on Slack through a [Slack Integration](/docs/slack-integration "Slack Integration").



<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        PowerShell
      </th>
      <th>
        Option Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **--payload**
      </td>
      <td>
        **-payload**
      </td>
      <td>
        (optional) A path to a valid json file to act as the payload of the message. If a payload is provided, all other parameters are ignored. This payload is directly sent to Slack, so please view the Slack API documentation for information on how the payload should be formatted.
      </td>
    </tr>
    <tr>
      <td>
        **--username**
      </td>
      <td>
        **-username**
      </td>
      <td>
        (optional) shows in the heading of the Slack message
      </td>
    </tr>
    <tr>
      <td>
        **--pretext**
      </td>
      <td>
        **-pretext**
      </td>
      <td>
        (optional) a string that becomes the first part of the Slack message. Defaults to current date/time
      </td>
    </tr>
    <tr>
      <td>
        **--text**
      </td>
      <td>
        **-text**
      </td>
      <td>
        (optional) the main text to display in the message.
      </td>
    </tr>
    <tr>
      <td>
        **--color**
      </td>
      <td>
        **-color**
      </td>
      <td>
        (optional) hex string that changes the color of the status bar to the left of the Slack message.
      </td>
    </tr>
    <tr>
      <td>
        **--recipient**
      </td>
      <td>
        **-recipient**
      </td>
      <td>
        (optional) the target of the message. Should start with “@” or “#” for user or channel, respectively.
      </td>
    </tr>
    <tr>
      <td>
        **--icon-url**
      </td>
      <td>
        **-icon-url**
      </td>
      <td>
        (optional) the url of the icon to show next to the message
      </td>
    </tr>
  </tbody>
</Table>



Sends an email through an [SMTP Credentials Integration](/docs/smtp-credentials-integration "SMTP Credentials Integration").



<Table>
  <thead>
    <tr>
      <th>
        Bash
      </th>
      <th>
        PowerShell
      </th>
      <th>
        Option Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **--recipients**
      </td>
      <td>
        **-recipients**
      </td>
      <td>
        one or more email addresses
      </td>
    </tr>
    <tr>
      <td>
        **--subject**
      </td>
      <td>
        **-subject**
      </td>
      <td>
        (optional) add a message to the subject. Does not replace the default subject
      </td>
    </tr>
    <tr>
      <td>
        **--body**
      </td>
      <td>
        **-body**
      </td>
      <td>
        (optional) specify some text to add to the body of the email. Does not replace the existing body information
      </td>
    </tr>
    <tr>
      <td>
        **--status**
      </td>
      <td>
        **-status**
      </td>
      <td>
        (optional) can be set to a valid status string. By default it will be set based on the section of scrip the command is executed in.
      </td>
    </tr>
    <tr>
      <td>
        **--attachments**
      </td>
      <td>
        **-attachments**
      </td>
      <td>
        (optional) a list of files to attach to the email. Combined total of all files cannot exceed 5MB
      </td>
    </tr>
    <tr>
      <td>
        **--attach-logs**
      </td>
      <td>
        **-attach-logs**
      </td>
      <td>
        (optional) ‘true’ or ‘false’. Defaults to false. All available logs for the step will be attached to the email. Note that it can only attach logs that have already been created, so using this option in the onStart section, for example, would not have very detailed logs.
      </td>
    </tr>
    <tr>
      <td>
        **--show-failing-commands**
      </td>
      <td>
        **-show-failing-commands**
      </td>
      <td>
        (optional) 'true’ or ‘false’. Defaults to false. The existing logs for the step will be parsed. Any failed command that is detected will be added to the body of the email, along with up to 100 preceding lines (if printed from the same command)
      </td>
    </tr>
  </tbody>
</Table>



Environment Options

All of the above options can also be included as environment variables instead of arguments. The command line argument will have priority over the environment. Here is the full list of ENVs:

* `NOTIFY_USERNAME` (--username/-username)
* `NOTIFY_PASSWORD` (--password/-password)
* `NOTIFY_RECIPIENT` (--recipient/-recipient)
* `NOTIFY_PRETEXT` (--pretext/-pretext)
* `NOTIFY_TEXT` (--text/-text)
* `NOTIFY_COLOR` (--color/-color)
* `NOTIFY_ICON_URL` (--icon-url/-icon-url)
* `NOTIFY_PAYLOAD` (--payload/-payload)
* `NOTIFY_TYPE` (--type/-type)
* `NOTIFY_PROJECT_ID` (--project-id/-project-id)
* `NOTIFY_ENVIRONMENT` (--environment/-environment)
* `NOTIFY_REVISION` (–revision/-revision)
* `NOTIFY_SUMMARY` (--summary/-summary)
* `NOTIFY_ATTACH_FILE` (--attach-file/-attach-file)
* `NOTIFY_REPOSITORY` (--repository/-repository)
* `NOTIFY_EMAIL` (–email--email/-email)
* `NOTIFY_STATUS` (--status/-status)
* `NOTIFY_VERSION` (--version/-version)
* `NOTIFY_CHANGELOG` (--changelog/-changelog)
* `NOTIFY_DESCRIPTION` (–description--description/-description)
* `NOTIFY_ATTACHMENTS` (–attachments--attachments/-attachments)
* `NOTIFY_ATTACH_LOGS` (--attach-logs/-attach-logs)
* `NOTIFY_SHOW_FAILING_COMMANDS` (--show-failing-commands/-show-failing-commands)
* `NOTIFY_SUBJECT` (--subject/-subject)
* `NOTIFY_BODY` (–body)

## JSON

The following JSON functions are available for Pipelines:

* [set\_payload](/docs/set_payload "set_payload")
* [read\_json](/docs/read_json "read_json")

### set_payload

**Description**

Sets an optional JSON payload (string or file) for an [OutgoingWebhook](/docs/outgoingwebhook "OutgoingWebhook") resource. When the OutgoingWebhook is specified in a step's `outputresources` the payload is sent when the step is complete.

**Usage**



<Table>
  <thead>
    <tr>
      <th>
        Shell
      </th>
      <th>
        Function
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Bash
      </td>
      <td>
        `set_payload <resource> <payload> [--file]`
      </td>
    </tr>
    <tr>
      <td>
        PowerShell
      </td>
      <td>
        `set_payload <resource> <payload> [-file]`
      </td>
    </tr>
  </tbody>
</Table>


