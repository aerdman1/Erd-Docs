---
title: My First Page with Content
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
# Schema Reference

BI Export lets you export account data for future import to the analytics tools. The data is stored in tables, which are connected using foreign key identifiers (like in a relational database). The following page describes the tables that are present in the export and their columns.

> **Please note:** The _audit\_log_ file in BI Data Export is limited to a maximum of 10,000,000 rows for the previous 180 days.

[See diagram](https://developers.wrike.com/uploads/cb09c5d2-7cd4-4d3e-884f-41b8d604d907/data-diagramgv.png?auto=compress%2Cformat&fit=min&fm=jpg&q=80&rect=1543%2C0%2C3504%2C1976)

---

## TABLE PARAMETERS

<Accordion title="attachment_file – Detailed information about file attachments" icon="fa-table">

| Column name | Type | Description | Primary key | Foreign key | Cardinality | Required |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| attachment_file_id | Number | Unique ID of attached file | yes | - | - | yes |
| attachment_file_api_id | String | API ID of attached file. Can be used to reference file via REST API or in backup | - | - | - | yes |
| attachment_file_content_height | Number | Height of image/video (if applicable) | - | - | - | - |
| attachment_file_content_width | Number | Width of image/video (if applicable) | - | - | - | - |
| attachment_file_name | String | Name of the attachment | - | - | - | yes |
| attachment_file_size_bytes | Number | Size of the attachment in bytes | - | - | - | yes |
| user_id | Number | ID of user who attached the file | - | FK user(user_id) | N:1 | yes |
| when_added | Date | Date when file was attached | - | - | - | yes |

</Accordion>

<Accordion title="audit_log – User's operations log" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="custom_field – Custom field definitions" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="group – User groups" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="group_to_user – Users membership in groups" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="recurrence – Information about recurrent tasks" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="timelog_category – Timelog categories" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="user – Users" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_assignee – Information about task assignees and project owners" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_attachment – Attaches for tasks, projects, folders" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_attachment_to_attachment_file – Versions of task/folder/project attachments" icon="fa-table">

| Column name | Type | Description | Primary key | Foreign key | Cardinality | Required |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| attachment_file_id | Number | ID of the file | yes | FK attachment_file(attachment_file_id) | 1:1 | yes |
| attachment_version | Number | Version of the file | - | - | - | yes |
| user_id | Number | ID of user that has added this version of the attachment | - | FK user(user_id) | N:1 | yes |
| when_added | Date | Date when the attachment was added in the comment | - | - | - | yes |
| work_attachment_id | Number | ID of the attachment | yes | FK work_attachment(work_attachment_id) | - | yes |
| work_comment_id | Number | Comment where the task was attached | - | FK work_comment(work_comment_id) | N:1 | yes |

</Accordion>

<Accordion title="work_change_revision – Change revisions (status, title, description etc.) of tasks, projects, and folders" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_comment – Information about comments in tasks, projects and folders" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_comment_content – Comment contents in tasks, projects, and folders" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_comment_to_mention – Mentions of groups and users in comments" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_custom_field – Custom field values" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_custom_field_history – Change history of task custom fields values" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_description – Task/project/folder descriptions in HTML format" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_folder – Detailed information about folders" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_graph – Information about parent and child relationships of projects, folders and tasks" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_item – Base information for tasks, projects, and folders" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_project – Detailed information about projects" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_project_to_task – Relationships between projects and tasks (for any level of nesting)" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_space – Information about spaces" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_space_user – Information about users of spaces" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_task – Detailed information about tasks" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_task_dependency – Task dependencies" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_timelog – Time logged for tasks" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_timelog_comment – Comments for timelogs" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_workflow_stage_history – History of task status changes" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="workflow – Workflows" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="workflow_stage – Workflow statuses" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>

<Accordion title="work_task_flexible_effort – Flexible effort for task" icon="fa-table">

> Column details not expanded in source. Expand this table in the Wrike BI Export schema reference for full column definitions.

</Accordion>