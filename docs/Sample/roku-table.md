---
title: Roku Table
deprecated: false
hidden: false
metadata:
  robots: index
---
### Asset

An asset represents a specific content item in the app's catalog. It contains all the metadata for displaying the content item in the Roku platform and deep linking directly into content when it is selected.

| Field | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required/Optional                                                |
| :---- | :----- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------- |
| id    | String | A maximum 50-character immutable unique ID for the content item. <br /><br />Once an ID is created for a content item in Roku Search, it may not be changed. <br /><br />The id must be unique within the feed. If the feed contains duplicate IDs, only one of the items with the duplicated ID is preserved. <br /><br />If the **type** for the content item is "externalIdOnly" set this field to the ID of the external source (for example, the Gracenote TMS ID). | Required, unless the  **type** for the content item is "season". |
| type  | Enum   | The media type of the content item:                                                                                                                                                                                                                                                                                                                                                                                                                                      |                                                                  |

### type \{#type}

<br />

* **movie**: Movie or long-form film (over 15 minutes).
  * **tvspecial**: One-time TV program that is not part of a series, or content that does not fit into any other mediaType category.
    * **series**: Set of related serialized episodes and possibly seasons.
      * **season**: As part of a series, single set of related TV episodes.
        * **episode**: Single content item (an episode of a TV show, for example).
          * **shortform**: Standalone content that is 15 minutes or less that is not a movie or TV show.
            * **externalIdOnly**: Validates the **id**, **externalIdSource**, and **playOptions** fields.