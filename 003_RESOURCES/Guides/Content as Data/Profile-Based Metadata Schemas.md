---
oct.type: sonnijqhve020z5jo6vhbetv
id: 446d508c-3666-490c-b011-2ce1238173ec
function: explanation
status: current
topics:
  - metadata
  - profiles
  - discovery
  - work
  - knowledge
created: '2026-08-15'
updated: '2026-08-15'
attribution:
  - ChatGPT
  - Theodore Sprencel
oct.note_width: full
---



# Profile-Based Metadata Schemas

> [!TIP]
> **Note**
> The contents of this document are drawn from, and therefore covered by, [[003_RESOURCES/Guides/Content as Data/Standard Metadata Toolset DOC]] . That document is the source of truth for the system in general. This document is currently being edited to become the Octarine Addendum to the system documentation.

> [!INFO]
> This is a method of assigning metadata to notes and documents in a simplified, tailored manner that still comports with most conventions and keeps content portable. At its core is a simple concept: Every note is a **Discovery**, **Work**, or **Knowledge** item. These are three tried-and-tested **Profiles** that have survived stress-testing and hole-poking and scrutiny from various angles.

This system is quite similar to Type-centered systems, but it makes the language clearer regarding what the content is actually supposed to do. And it enables anyone to tweak details to their own preferences.

---

[[Octarine-Organized-Notes-20260815.gif]]

The GIF shows Octarine’s default Organised Notes view: every note in the Notes location, sorted by modification date. So its delightful junk-drawer quality is intentional, not evidence of how your eventual profile views will look. Views can select system and custom fields, then filter, sort, group, and display them as tables, Kanban boards, or graphs.

## Octarine Views documentation

More importantly, Octarine does persist the assigned type in each note’s frontmatter:

`oct.type: discovery`

Its type definitions live separately in `.octarine/types.json`, but the assigned value travels with the Markdown note.

## Octarine Note Types documentation

That settles our earlier decision:

> [!SUCCESS]
> **Decision**
> Do not add a duplicate profile property in Octarine.

Instead, document this mapping:

<!--octarine-table-cols:300,187,196,358-->
| Concept | Canonical model | Octarine storage | Octarine display |
| --- | --- | --- | --- |
| Overarching content classification | **profile** | **oct.type** | **Note Type** |
| Content about discovery activities — i.e., gathering and making sense of information before starting work. | `profile`: `discovery` | `oct.type`: `discovery` | Discovery |
| Content that aides work. | `profile`: `work` | `oct.type`: `work` | Work |
| Content that records established information for record-keeping, reference, tracking, learning, etc. | `profile`: `knowledge` | `oct.type`: `knowledge` | Knowledge |

[[Octarine_Note_Types_config_Profiles_highlight.png]]

 

Another application may not understand the `oct.` namespace automatically, but the classification remains plainly readable and mechanically mappable. Duplication would provide little benefit while creating an opportunity for oct.type: discovery and profile: knowledge to disagree.

### The storage model

The documentation reveals a clean separation:

Data

Storage

Note content

Markdown files

Property values

YAML frontmatter in each note

Type assignment

oct.type in frontmatter

Property definitions

.octarine/properties.json

Type schemas

.octarine/types.json

Saved views

.octarine/views.json

Saved semantic relationships

oct.related in frontmatter

Rebuildable AI index

.octarine/embeddings.sqlite

So the individual note data is portable, while Octarine’s richer schema definitions and interfaces travel with the .octarine folder. A complete backup should include the whole workspace, not merely the visible Markdown.

Octarine data-storage documentation

Four different kinds of connection

The documentation also lets us distinguish some things I had previously compressed together:

Octarine concept

Meaning

Linked Notes

Notes explicitly linked from the current note

References

Other notes that link to or mention the current note

Related Notes

Semantically similar notes suggested by the local embedding index

oct.related

Related Notes relationships deliberately saved to frontmatter

Our custom references

Resources intentionally selected for further information, evidence, or context

Octarine’s References feature is specifically inbound: wikilinks and unlinked plain-text mentions pointing toward the current note.

Octarine References documentation

Related Notes begins as AI-assisted semantic similarity and becomes durable only when a suggestion is explicitly saved to oct.related.

Octarine Meta Sidebar documentation

That means our custom references property remains semantically legitimate, but there is a naming collision in the interface:

References in Octarine: “Where is this note referenced?”

references in our schema: “Where should I go for more information?”

I wouldn’t rename it preemptively, but we should watch whether that collision causes hesitation during actual use.

One final practical test remains: Octarine describes List properties as predefined multi-select options that also support wikilinks. That is ideal for controlled topics, but references and attribution are open-ended. We should test whether adding arbitrary URLs, people, and note links feels natural or whether those values awkwardly become permanent dropdown options.

Octarine Properties documentation

So yes: the documentation materially improved the picture. Octarine is storing more of this portably than we had established, and the default mega-table was simply the warehouse floor—not the showroom.

---

## How Profiles work

When a note is assigned one of the three **Profiles**, it cascades the properties that are part of that note's metadata. So far we've only dealt with YAML frontmatter, but there's no reason we couldn't explore the system in other contexts.

<!--octarine-table-cols:117,0-->
| Treatment | Properties |
| --- | --- |
| Same definition across all profiles | `id`, `topics`, `created`, `updated`, `sources` |
| Profile-specific values and definitions | `function`, `status` |
| Work-only | `project`, `due` |

### ~🟢Shared definitions~

Use these unchanged across all three profiles:

<!--octarine-table-cols:133,0-->
| Property | Definition |
| --- | --- |
| `id` | Stable, unique identifier that survives renaming or relocation. Format: `YYYYMMDD-###`, where `###` is a zero-padded daily sequence. |
| `topics` | Subjects the artifact is principally about. Enter one or more concise, reusable terms in lowercase kebab-case, such as `metadata`, `color-theory`, or `content-modeling`. |
| `created` | App-generated creation date and time. Format: ISO 8601 timestamp. |
| `updated` | App-generated date and time of the most recent modification. Format: ISO 8601 timestamp. |
| `sources` | ~~Sources from which the artifact’s content or context was derived. Enter one or more URLs, citations, people, conversations, events, applications, or related artifacts.~~ |

#### Note on List Items

`topics` and `sources` should ideally be typed as lists or multiple-value text fields. If an app only permits scalar text, we should explicitly choose a delimiter rather than leaving the representation ambiguous.

### ~🟡Profile-specific ~`function`

<!--octarine-table-cols:142,0-->
| Profile | Copy-ready definition |
| --- | --- |
| Discovery | What this discovery artifact primarily does. Allowed values: `capture` (preserves an input or observation), `question` (records an unresolved inquiry), `explore` (develops an idea or possibility), or `collect` (assembles related inputs or examples). |
| Work | What this work artifact primarily does. Allowed values: `plan` (defines intended outcomes, actions, or sequencing), `decide` (frames, makes, or records a choice), `track` (maintains visibility into progress or obligations), `investigate` (resolves a question for current work), `produce` (develops an intended output), or `distill` (extracts reusable knowledge from contextual material). |
| Knowledge | What this knowledge artifact primarily does. Allowed values: `overview` (provides broad orientation), `explanation` (develops understanding of how or why something works), `how-to` (enables completion of a particular task), `reference` (provides information for selective consultation), `definition` (establishes a concept’s meaning and boundaries), or `synthesis` (combines multiple inputs into a coherent understanding). |

#### Note about activity logs

One likely pressure point is meeting notes or activity logs. They don’t fit the initial Work vocabulary perfectly. I would test actual notes before adding `record`; that’s exactly the sort of value that should enter because the corpus demands it.

### ~🟡Profile-specific ~`status`

<!--octarine-table-cols:144,0-->
| Profile | Copy-ready definition |
| --- | --- |
| Discovery | Current state of the discovery. Allowed values: `new` (not yet reviewed), `active` (being explored), `parked`(retained for possible later attention), `resolved` (the inquiry or exploration has concluded), or `closed` (no further attention is planned). |
| Work | Current execution state of the work. Allowed values: `not-started` (recognized but not underway), `in-progress` (currently being advanced), `waiting` (paused until an expected event occurs), `blocked` (unable to proceed without intervention), `deferred` (intentionally postponed), `in-review` (awaiting feedback or approval), `done` (completed), or `cancelled` (ended before completion). |
| Knowledge | Current usability state of the knowledge artifact. Allowed values: `draft` (still being developed), `current`(available for normal use), `needs-review` (requires verification or revision), `superseded` (replaced by a newer identified artifact), or `archived` (inactive and retained primarily for history). |

The `waiting`/`blocked` distinction is worth the extra value: waiting may be healthy; blocked requires attention.

### ~🟡Work-only definitions~

| Property | Recommended definition |
| --- | --- |
| `project` | Project to which the work artifact contributes. Format: a single internal reference to the corresponding project artifact. |
| `due` | Target date by which the work should be completed. Format: `YYYY-MM-DD`. |

I’d rename the current `Due Date` property ID to `due`, while retaining “Due Date” as its display name. That keeps the machine-facing property names consistent.