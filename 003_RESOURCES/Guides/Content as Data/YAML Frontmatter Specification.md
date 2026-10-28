---
oct.type: w0qat0kve8czsly6xhf2pqbh
id: 11161384-6711-4e59-9e75-d9e327c16cb9
function: reference
status: superseded
topics:
  - yaml-frontmatter
  - knowledge-management
created: '2026-07-01'
updated: 2026-09-06T03:25
references:
  - '[[003_RESOURCES/Guides/Content as Data/Profile-Based Metadata Schemas]]'
attribution:
  - ChatGPT / Codex
---








































Default frontmatter properties and values that can be used as a starting point for most projects.

---

## Default Frontmatter Properties and Values

These fields can be copied into new documents as a starting point, just be sure to delete what you don't need down to the space! YAML can be very picky about formatting. Remember the `tab` is never used, only the space bar.

```yaml
---
id: YYYYMMDD-APP-##
title: Title of File
aliases:
  - "Alias One"
  - "Alias Two"
created: MM-DD-YYYY
updated: MM-DD-YYYY
type: choose-type
subtype: add-subtype
system: choose-system
process: choose-process
status: choose-status
source: add-source
description: > Optional. Use folded scalar for multi-line.
tags: []
---
```

### Property Details

Options, guidelines and restrictions.

- **id**: stable UID, survives renames
- **title**: Title of File; only if different from filename
- **aliases**: Other names by which the content is known
- **created**: Date of first save; only needed if app doesn't build this into system
- **updated**: Date of last save; only needed if app doesn't build this into system
- **type**: note | guide | sop | reusable | readme | spec
- **subtype**: e.g. standard, agents, colors, font
- **system**: ai | content | design | development | documentation | operations
- **process**: automation | classification | deprecation | optimization | orchestration | organization | production
- **status**: rejected | deferred | todo | doing | refining | done | evergreen
- **source**: URL, book, conversation, etc.
- **description**: *See code block.*
- **tags**: [tag-one, tag-two, tag-three]