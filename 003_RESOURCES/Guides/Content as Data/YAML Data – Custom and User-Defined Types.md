---
oct.type: t9k19r1mxuxg2uxoa1kdbcd5
oct.related:
  - '[[003_RESOURCES/Guides/Content as Data/YAML Data Types Overview]]'
id: 6377cc68-a924-4af5-a46d-a2451730be79
aliases: YAML Data Lesson – Part 2
subject_matter: YAML data, anchors, aliases, and custom types
system:
  - resources
source: Google AI Mode Search
Author: Various
AI Assistance: true
description: >-
  In Part 2 of the impromptu lesson, covers anchors, aliases, YAML flexibility,
  and more.
tags:
  - yaml-data
  - custom-yaml-types
created: '2026-06-16'
updated: '2026-06-19'
status: done
---








































































> [!INFO]
> In Part 2 of my impromptu lesson from Google AI Mode Search about YAML data, we cover anchors, aliases, YAML flexibility and more.

## From Google AI Mode Search

### Anchors and Aliases (Data Referencing)

Anchors and aliases allow you to reuse data without duplicating it. You mark a reusable section with an ampersand (`&`) and reference it elsewhere with an asterisk (`*`). [1, 2, 3]

You can also use the merge key (`<<`) to import and extend entire maps. [4]

```yaml
# 1. Defining reusable data with an anchor (&)
default_settings: &base_config
  timeout: 30
  retries: 3
  environment: production

# 2. Referencing the exact same data using an alias (*)
api_service: *base_config

# 3. Merging and overriding values using the merge key (<<)
db_service:
  <<: *base_config
  timeout: 60        # Overrides the default timeout value
  port: 5432         # Adds a new key unique to this service
```

### Custom and User-Defined Types

YAML allows you to define custom data types using explicit tags starting with an exclamation mark (`!`). These tags act as metadata, telling your application framework or parser how to convert a specific YAML block into a custom programming object or class. [5, 6, 7, 8]

```yaml
# Single exclamation mark (!) denotes a custom domain-specific application tag
coordinates: !Point
  x: 45.3
  y: -12.1

# Double exclamation marks (!!) represent standard, built-in YAML types
forced_string: !!int 12345    # Forces a number to be parsed as a string

# Used widely in infrastructure tools like AWS CloudFormation
database_url: !Join [ "-", [ "prod", "db", "cluster" ] ]
```

### Parsing Custom Types in Code

Because custom tags are unique to your application, your code parser must be explicitly configured to read them.

```python
import yaml

# Define the custom object class
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

# Create a constructor function for the parser
def point_constructor(loader, node):
    fields = loader.construct_mapping(node)
    return Point(**fields)

# Register the custom tag parser
yaml.add_constructor('!Point', point_constructor)

# Now, loading a YAML file with `!Point` will output a Python Point object
```

---

## Footnotes

[1] [https://dev.to](https://dev.to)

[2] [https://realpython.com](https://realpython.com)

[3] [https://docs.celigo.com](https://docs.celigo.com)

[4] [https://dev.to](https://dev.to)

[5] [https://orhanergun.net](https://orhanergun.net)

[6] [https://symfony.com](https://symfony.com)

[7] [https://dev.to](https://dev.to)

[8] [https://realpython.com](https://realpython.com)