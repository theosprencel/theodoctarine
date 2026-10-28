---
oct.type: w0qat0kve8czsly6xhf2pqbh
id: 918bb799-802b-4f44-8a9d-7263b051d596
function: reference
status: needs-review
topics:
  - octarine-data
  - metadata
Created: '2026-07-01'
updated: 2026-09-06T03:33
references:
  - https://docs.octarine.app/getting-started/meet-octarine
---























































Built-in data that can be attached to notes out of the box and used in Views.

---

## Data Fields

Built-in metadata tracked by Octarine:

| **Field** | **Description** | **Type** |
| --- | --- | --- |
| Name | Note filename | string |
| Path | Full file path | string |
| Folder | Folder path excluding the workspace path | string |
| Location | Daily, Weekly, Templates, or Notes folder | list |
| Created Date | When the note was created | date |
| Modified Date | When the note was last edited | date |
| Tags | Tags from properties frontmatter | tags |
| Linked Notes | Files referenced in note | list |
| Linked Media | Attachments referenced in note | list |
| Linked Files | External files referenced in note | list |
| Task Status | Pending, Complete, or No Tasks | list |
| Is Pinned | Note is pinned in file tree | boolean |
| Is Locked | Note is read-only | boolean |

Custom properties you've defined in your workspace are also available as filter fields. See [**~Properties~**](https://docs.octarine.app/note-management/properties) for more.

### [**Filter Operators**](https://docs.octarine.app/organization/views#filter-operators)

Available operators depend on the field type:

| **Type** | **Operators** |
| --- | --- |
| **String** | equals, does not equal, contains, does not contain, starts with, ends with, is empty, is not empty |
| **Number** | equals, does not equal, greater than, less than, greater than or equal, less than or equal, is empty, is not empty |
| **Date/Time** | is, is before, is after, is empty, is not empty |
| **Boolean** | is, is not |
| **List/Tags** | is any of, is not any of, is empty, is not empty |
| **Files** | is empty, is not empty |

### [**Date Shortcuts**](https://docs.octarine.app/organization/views#date-shortcuts)

When filtering by dates, use relative options like `Today`, `Yesterday`, `Last 7 Days`, `Last Week`, `Last Month`, `This Quarter`, or pick a specific date from the calendar.

## [**Columns**](https://docs.octarine.app/organization/views#columns)

Columns control which data fields appear in your view table.

### [**Managing Columns**](https://docs.octarine.app/organization/views#managing-columns)

1. Click the columns icon in the view header
2. Toggle checkboxes to show or hide columns
3. Drag to reorder columns

The Name column is always pinned to the left and stays visible when scrolling horizontally.

### [**Column Types**](https://docs.octarine.app/organization/views#column-types)

Each column renders data based on its type:

| **Type** | **Display** |
| --- | --- |
| **String** | Plain text (supports doclinks) |
| **Number** | Right-aligned numeric values |
| **Date/DateTime** | Formatted dates and times |
| **Checkbox** | Visual checkmark or empty state |
| **List** | Comma-separated values |
| **Tags** | Color-coded tag pills |
| **Tasks** | Task count and status indicator |
| **Links** | Clickable note/file references |
