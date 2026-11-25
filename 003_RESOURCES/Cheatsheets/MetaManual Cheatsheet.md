---
oct.type: w0qat0kve8czsly6xhf2pqbh
id: 0e354c4b-af0f-4bed-8526-dd018ed22396
function: reference
status: usable
topics:
  - metamanual
  - metadata-system
  - cheatsheets
created: '2026-11-26'
updated: '2026-11-26'
---

> [!INFO]
> A guide to help you determine the profile value, and therefore the entire set of metadata, to assign to any discovery, work, or knowledge artifact.

# MetaManual System Cheatsheet

MetaManual is a guide to helping anyone work with metadata and assign useful information to notes, documents, and research materials. This cheatsheet is a quick reference for all three Profiles — Discovery, Work, and Knowledge — with properties and values that accompany each. The goal is to help anyone, regardless of experience with metadata, YAML frontmatter, or knowledge management, assign meaningful attributes to make their working materials even more helpful.

## Profile Models

### Discovery

```yaml
id: {uuid}
profile: discovery
function: #  capture | question | explore | collect
status: #  new | active | parked | resolved | closed
topics: #  Enter one or more concise, reusable terms in kebab-case, such as metadata, color-theory, or content-modeling.
created: {YYYY-MM-DDTHH:mm:ss}
updated: {YYYY-MM-DDTHH:mm:ss}
references: #  Resources for additional information, evidence, or context. Format as list items.
attribution: #  People, organizations, or works whose ideas, information, or contributions should get credit. Format as list items.
```

### Work

```yaml
id: {uuid}
profile: work
function: #  plan | decide | track | investigate | produce | distill | correct
status: #  not-started | in-progress | waiting | blocked | deferred | in-review | done | canceled
topics: #  Enter one or more concise, reusable terms in kebab-case, such as metadata, color-theory, or content-modeling.
created: {YYYY-MM-DDTHH:mm:ss}
updated: {YYYY-MM-DDTHH:mm:ss}
references: #  Resources for additional information, evidence, or context. Format as list items.
attribution: #  People, organizations, or works whose ideas, information, or contributions should get credit. Format as list items.
project: #  Project artifact contributes to. Format: a single internal reference to the corresponding project artifact.
due: #  Target date by which the work should be completed. Format: {YYYY-MM-DD}
```

### Knowledge

```yaml
id: {uuid}
profile: discovery
function: #  overview | explanation | how-to | reference | definition | synthesis
status: #  draft | usable | needs-review | superseded | archived
topics: #  Enter one or more concise, reusable terms in kebab-case, such as metadata, color-theory, or content-modeling.
created: {YYYY-MM-DDTHH:mm:ss}
updated: {YYYY-MM-DDTHH:mm:ss}
references: #  Resources for additional information, evidence, or context. Format as list items.
attribution: #  People, organizations, or works whose ideas, information, or contributions should get credit. Format as list items.
```

## Visual Overview

```mermaid
flowchart TB
M["MetaManual"] --> P["Profiles"]
P --> D["Discovery"] & W["Work"] & K["Knowledge"]

D --> DY["<pre>Discovery:<br/>  uuid: {uuid}<br/>  profile: discovery<br/>  function: # capture | question | explore | collect<br/>  status: # new | active | parked | resolved | closed<br/>  topics: # shared<br/>  created: # shared<br/>  updated: # shared<br/>  references: # shared<br/>  attribution: # shared</pre>"]

W --> WY["<pre>Work:<br/>  uuid: {uuid}<br/>  profile: work<br/>  function: # plan | decide | track | investigate | produce | distill | correct<br/>  status: # not-started | in-progress | waiting | blocked | deferred | in-review | done | cancelled<br/>  topics: # shared<br/>  created: # shared<br/>  updated: # shared<br/>  references: # shared<br/>  attribution: # shared<br/>  project: # Work-specific<br/>  due: # Work-specific</pre>"]

K --> KY["<pre>Knowledge:<br/>  uuid: {uuid}<br/>  profile: knowledge<br/>  function: # overview | explanation | how-to | reference | definition | synthesis<br/>  status: # draft | active | needs-review | superseded | archived<br/>  topics: # shared<br/>  created: # shared<br/>  updated: # shared<br/>  references: # shared<br/>  attribution: # shared</pre>"]

S["<pre>Shared fields:<br/>  uuid: {uuid}<br/>  profile: # shared with fixed values<br/>  topics: # concise and reusable terms determined by content<br/>  created: {YYYY}-{MM}-{DD}T{HH:mm:ssZ}<br/>  updated: {YYYY}-{MM}-{DD}T{HH:mm:ssZ}<br/>  references: # Where to get more info<br/>  attribution: Who or what should get credit</pre>"]

    S -.-> DY
    S -.-> WY
    S -.-> KY

    classDef root fill:#eef2ff,stroke:#818cf8,stroke-width:2px,color:#000000,text-align:left;
    classDef profile fill:#f0fdfa,stroke:#2dd4bf,stroke-width:2px,color:#000000,text-align:left;
    classDef data_discovery fill:#ecfeff,stroke:#22d3ee,stroke-width:1px,color:#000000,text-align:left;
    classDef data_work fill:#fff7ed,stroke:#fb923c,stroke-width:1px,color:#000000,text-align:left;
    classDef data_knowledge fill:#f5f3ff,stroke:#a78bfa,stroke-width:1px,color:#000000,text-align:left;
    classDef shared fill:#f0fdf4,stroke:#4ade80,stroke-width:1px,color:#000000,text-align:left;

    class M,P root;
    class D,W,K profile;
    class DY data_discovery;
    class WY data_work;
    class KY data_knowledge;
    class S shared;
```