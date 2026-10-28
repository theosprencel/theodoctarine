---
oct.type: t9k19r1mxuxg2uxoa1kdbcd5
id: e20e9095-6ace-4e49-ba65-225eafb0e5a6
created: '2026-06-16'
updated: '2026-06-16'
subject_matter: YAML data types
system:
  - resources
source: Google AI Mode Search
Author: Various
AI Assistance: true
description: >-
  A very high-level summary of YAML data types, covering scalars, sequences, and
  mappings.
tags:
  - yaml-data-types
  - scalar-data
  - data-array
  - data-mapping
oct.related:
  - >-
    [[003_RESOURCES/Guides/Content as Data/YAML Data – Custom and User-Defined
    Types]]
status: done
aliases: '[YAML Data Cheat Sheet]'
---






























































> [!INFO]
> A very high-level summary (from Google AI Overview) of YAML data types, numbered because there will likely be more such notes to come.

---

## From Google AI Overview

YAML natively supports three primary primitives: scalars (basic values), sequences (lists), and mappings (dictionaries). The data serialization language automatically detects specific types based on how values are formatted, but you can also use explicit tags (like `!str`  or `!int`) to force a particular type. [[~1~](https://yaml.org/spec/1.2.2/#:~:text=Introduction%20to%20YAML.%20YAML%20\(a%20recursive%20acronym,to%20be%20human%2Dfriendly%20and%20work%20well%20w), [~2~](https://harshitawrites.hashnode.dev/yaml-datatypes#:~:text=In%20programming%2C%20strings%20are%20typically%20enclosed%20within,without%20quotes.%20Although%20strings%20can%20be%20written), [~3~](https://dlang-community.github.io/D-YAML/tutorials/custom_types.html#:~:text=Sometimes%20you%20need%20to%20serialize%20complex%20data,mappings%20with%20classes'%20fields.%20YAML%20also%20suppor), [~4~](https://yaml.irz.fr/types.html#:~:text=Many%20more%20advanced%20data%20types%2C%20such%20as,implementations.%20Finally%20YAML%20defines%20a%20way%20t)]

The native data types supported in YAML Specifications include the following categories: [[~1~](https://yaml.org/spec/1.2.2/#:~:text=Introduction%20to%20YAML.%20YAML%20\(a%20recursive%20acronym,to%20be%20human%2Dfriendly%20and%20work%20well%20w), [~5~](https://en.wikipedia.org/wiki/YAML#:~:text=Custom%20data%20types%20are%20allowed%2C%20but%20YAML,associative%20arrays%20\(also%20known%20as%20maps%2C%20dic), [~6~](https://www.networkacademy.io/ccna-automation/data-formats/yaml-data-types#:~:text=Basic%20Data%20Types.%20YAML%20was%20designed%20to,/%20dictionaries\);%20*%20sequences%20\(arrays%20/%20lists\);)]

### 1. Scalars (Single Values)

Scalars are the most basic data types and represent individual units of data.

- **Strings**: Plain text that typically requires no quotation marks. You can wrap them in single quotes ('text') to prevent evaluation or double quotes ("text") to allow escape characters.

- **Multi-line Strings**: Created using the literal operator to preserve newlines, or the folded operator to convert line breaks into spaces.

- **Integers**: Whole numbers written in standard decimal notation, binary (0b), octal (0o), or hexadecimal (0x) formats.

- **Floating-Point Numbers**: Fractional numbers, including standard decimals, scientific notation, and special values like (infinity) or (Not a Number).

- **Booleans**: Logical values representing true or false states. YAML 1.2 recognizes and `true` and `false`.

- **Nulls**: Empty or undefined values denoted by writing `null`, `~`, or leaving the value blank. [[~6~](https://www.networkacademy.io/ccna-automation/data-formats/yaml-data-types#:~:text=Basic%20Data%20Types.%20YAML%20was%20designed%20to,/%20dictionaries\);%20*%20sequences%20\(arrays%20/%20lists\);), [~8~](https://www.ibm.com/think/topics/yaml#:~:text=YAML%20syntax%20and%20attributes%20*%20There%20are,understand%20the%20structure%2C%20data%20types%20and%20c), [~22~](https://www.yaml.info/learn/), [~23~](https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started#:~:text=Handling%20Null%20Values%20in%20YAML%20You%20enter,literal.%20Python's%20representation%20for%20null%20is%20None.), [~24~](https://yaml.org/spec/1.2.2/ext/glossary/#:~:text=A%20data%20type%20representing%20nothing%20or%20the,Typically%2C%20schemas%20will%20interpret%20the%20plain%20sca)]

### 2. Sequences (Lists / Arrays)

Sequences are ordered collections of items where each element is indexed.

- **Block Style:** Items are grouped using a hyphen followed by a space (`- `) on separate, indented lines.

- **Flow Style**: Items are written inline, wrapped in square brackets, and separated by commas (e.g., `[item1, item2]` ). [[~25~](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/?view=azure-pipelines#:~:text=YAML%20schema%20documentation%20conventions.%20The%20YAML%20schema,It%20includes%20a%20catalog%20of%20all%20s), [~26~](https://www.rudderstack.com/docs/profiles/dev-docs/yaml-refresher/#:~:text=Data%20types%20in%20YAML%20YAML%20supports%20several,Sequences:%20Represent%20lists%20and%20are%20denoted%20using), [~27~](https://www.youtube.com/watch?v=1HPs0ycPr1A#:~:text=and%20I%20would%20recommend%20that%20you%20go,see%20that%20YAML%20is%20a%20data%20serializatio), [~28~](https://symfony.com/doc/current/reference/formats/yaml.html), [~29~](https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html#:~:text=Lists%20and%20dictionaries%20%2D%20YAML%20block%20structures,collection%2C%20which%20is%20a%20list%2C%20or%20dictio)]

### 3. Mappings (Dictionaries / Hashes)

Mappings are unordered collections of key-value pairs separated by a colon and a space (`: `).

- **Block Style**: Pairs are organized using consistent indentation to build structural hierarchy.

- **Flow Style**: Pairs are written inline, enclosed in curly braces, and separated by commas (e.g., `{key1: value1, key2: value2}`). [[~1~](https://yaml.org/spec/1.2.2/#:~:text=Introduction%20to%20YAML.%20YAML%20\(a%20recursive%20acronym,to%20be%20human%2Dfriendly%20and%20work%20well%20w), [~25~](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/?view=azure-pipelines#:~:text=YAML%20schema%20documentation%20conventions.%20The%20YAML%20schema,It%20includes%20a%20catalog%20of%20all%20s), [~28~](https://symfony.com/doc/current/reference/formats/yaml.html), [~30~](https://about.gitlab.com/topics/devops/what-is-yaml/#:~:text=What%20is%20a%20YAML%20file?%20YAML%20files,YAML%20mimics%20natural%20language%20and%20uses%20str), [~31~](https://dev.to/kalkwst/a-gentle-introduction-to-the-yaml-format-bi6#:~:text=Flow%20mappings%20use%20curly%20brackets%20\(%20%7B%7D,key%2Dvalue%20pair%20within%20a%20mapping%20is%20separa)]

## Code Example

The following snippet demonstrates how these data types are structured in a standard file according to [CloudBees YAML Guidance](https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started):

```yaml
# Scalars
string_plain: Hello World
string_quoted: "Contains an escape sequence \n"
string_literal: |
  This block preserves
  every single newline.
string_folded: >
  This block collapses
  newlines into spaces.
integer_val: 42
float_val: 3.14159
boolean_val: true
null_val: null

# Sequences (Lists)
block_sequence:
  - Apple
  - Banana
flow_sequence: [Orange, Grape]

# Mappings (Dictionaries)
block_mapping:
  name: John Doe
  role: Developer
flow_mapping: {status: active, level: 5}
```

---

## Footnotes

[1] [~https://yaml.org/spec/1.2.2/~](https://yaml.org/spec/1.2.2/)

[2] [~https://harshitawrites.hashnode.dev/yaml-datatypes~](https://harshitawrites.hashnode.dev/yaml-datatypes)

[3] [~https://dlang-community.github.io/D-YAML/tutorials/custom_types.html~](https://dlang-community.github.io/D-YAML/tutorials/custom_types.html)

[4] [~https://yaml.irz.fr/types.html~](https://yaml.irz.fr/types.html)

[5] [~https://en.wikipedia.org/wiki/YAML~](https://en.wikipedia.org/wiki/YAML)

[6] [~https://www.networkacademy.io/ccna-automation/data-formats/yaml-data-types~](https://www.networkacademy.io/ccna-automation/data-formats/yaml-data-types)

[7] [~https://dev.to/kalkwst/a-gentle-introduction-to-the-yaml-format-bi6~](https://dev.to/kalkwst/a-gentle-introduction-to-the-yaml-format-bi6)

[8] [~https://www.ibm.com/think/topics/yaml~](https://www.ibm.com/think/topics/yaml)

[9] [~https://www.ibm.com/think/topics/yaml~](https://www.ibm.com/think/topics/yaml)

[10] [~https://yandex.cloud/en/docs/compute/concepts/instance-groups/specification~](https://yandex.cloud/en/docs/compute/concepts/instance-groups/specification)

[11] [~https://moodle2.units.it/pluginfile.php/762148/mod_resource/content/1/lecture-07.pdf~](https://moodle2.units.it/pluginfile.php/762148/mod_resource/content/1/lecture-07.pdf)

[12] [~https://blog.leena.ai/glossary/yaml/~](https://blog.leena.ai/glossary/yaml/)

[13] [~https://github.com/hadashiA/VYaml~](https://github.com/hadashiA/VYaml)

[14] [~https://devoriales.com/learn-yaml-with-python~](https://devoriales.com/learn-yaml-with-python)

[15] [~https://nestedtext.org/en/latest/alternatives.html~](https://nestedtext.org/en/latest/alternatives.html)

[16] [~https://go.dev/ref/spec~](https://go.dev/ref/spec)

[17] [~https://medium.com/@adisornbaimorakot/java-data-type-tutorial-java-int-data-type-735f693ffd30~](https://medium.com/@adisornbaimorakot/java-data-type-tutorial-java-int-data-type-735f693ffd30)

[18] [~https://www.commonwl.org/user_guide/topics/yaml-guide.html~](https://www.commonwl.org/user_guide/topics/yaml-guide.html)

[19] [~https://www.kerno.io/blog/yaml-file-format-complete-guide~](https://www.kerno.io/blog/yaml-file-format-complete-guide)

[20] [~https://www.youtube.com/watch?v=rGOvugNq6sM~](https://www.youtube.com/watch?v=rGOvugNq6sM)

[21] [~https://www.digitalocean.com/community/tutorials/understanding-data-types-in-php~](https://www.digitalocean.com/community/tutorials/understanding-data-types-in-php)

[22] [~https://www.yaml.info/learn/~](https://www.yaml.info/learn/)

[23] [~https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started~](https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started)

[24] [~https://yaml.org/spec/1.2.2/ext/glossary/~](https://yaml.org/spec/1.2.2/ext/glossary/)

[25] [~https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/?view=azure-pipelines~](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/?view=azure-pipelines)

[26] [~https://www.rudderstack.com/docs/profiles/dev-docs/yaml-refresher/~](https://www.rudderstack.com/docs/profiles/dev-docs/yaml-refresher/)

[27] [~https://www.youtube.com/watch?v=1HPs0ycPr1A~](https://www.youtube.com/watch?v=1HPs0ycPr1A)

[28] [~https://symfony.com/doc/current/reference/formats/yaml.html~](https://symfony.com/doc/current/reference/formats/yaml.html)

[29] [~https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html~](https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html)

[30] [~https://about.gitlab.com/topics/devops/what-is-yaml/~](https://about.gitlab.com/topics/devops/what-is-yaml/)

[31] [~https://dev.to/kalkwst/a-gentle-introduction-to-the-yaml-format-bi6~](https://dev.to/kalkwst/a-gentle-introduction-to-the-yaml-format-bi6)