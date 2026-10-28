---
oct.type: jcqsatv20htd8olifffaod97
id: 6db3d21a-ed85-458e-ac2c-779eec8922d5
aliases: '[Why use snake case]'
system:
  - resources
source: Google AI Mode Search
description: >-
  > Explanation from a Google AI Mode search why `snake_case` is preferable to
  `kebab-case` in many file-naming scenarios.
tags:
  - snake_case
  - file_naming_conventions
  - kebab-case
AI Assistance: false
Author: ''
Status: []
oct.related: ''
created: '2026-06-16'
updated: '2026-06-16'
Last Edited: '2026-06-19'
status:
  - Done
---
































































> [!INFO]
> Explanation from a Google AI Mode search why `snake_case` is preferable to `kebab-case` in many file-naming scenarios.

## ~🔵From Google AI Mode Search~

Your intuition is spot on. The massive rise of AI, Large Language Models (LLMs), and automated AI coding agents has heavily tilted the scales in favor of **snake_case** (`yaml_data_types`). [1, 2]

While kebab-case (`yaml-data-types`) remains king for web URLs and CSS, **snake_case provides distinct functional advantages for AI and programmatic workflows**. [1, 3, 4]

### **1. Tokenization and Prompt Efficiency [1]**

LLMs do not read words; they read "tokens" (chunks of characters). How text is broken down directly impacts an AI's comprehension speed, output speed, and your API cost. [2, 5, 6, 7]

- **The Kebab Problem**: Because a hyphen (`-`) is mathematically a subtraction sign, tokenizers frequently split a string like `yaml-data-types` into individual fragments (`yaml`, `-`, `data`, `-`, `types`). This wastes token space. [1, 8, 9, 10]
- **The Snake Advantage**: Modern tokenizers routinely group underscores directly with their surrounding letters. A phrase like `yaml_data_types` often compresses into fewer total tokens, making it [more token-efficient for AI contexts](https://michaellinus.medium.com/writing-token-efficient-context-files-for-ai-agents-a-practical-guide-e7ab18c20eea).[1, 11]

### **2. Code Compatibility for AI Agents**

AI agents (like GitHub Copilot or Cursor) frequently scrape, reference, and manipulate your workspace files using automated scripts behind the scenes. [1, 2]

- In almost all major programming languages (Python, SQL, JavaScript, C++), a hyphen is an invalid character for object, variable, or database names because the interpreter reads it as a minus sign. [8, 9, 12, 13]
- `yaml_data_types` is a globally legal code identifier. If an AI needs to turn your file list into a valid database table, an array of strings, or a programming variable, **snake_case maps perfectly 1:1 without breaking code execution**. [1, 14, 15]

### **3. Native Integration with OpenTelemetry and Infrastructure**

As AI systems shift toward complex pipelines, developer tools are standardizing file conventions to prevent translation bugs. Downstream AI monitoring infrastructure and observability pipelines (like Prometheus and OpenTelemetry semantic conventions) [force snake_case globally](https://github.com/QwenLM/qwen-code/issues/4419). Using snake_case for your underlying files removes the need for an AI to constantly convert styles between systems. [1]

## ~🔵The Bottom Line~

If your long-term goal is a pure, human-facing website or blog, stick with **kebab-case** for clean URLs. But if you want to build a future-proof knowledge base optimized for **AI indexing, automated scripting, LLM tools, or programming integrations**, **snake_case** gives you the definitive systemic edge. [1, 14, 16]

---

## ~🔵Footnotes~

[1] [https://github.com](https://github.com)

[2] [https://medium.com](https://medium.com)

[3] [https://smartwp.com](https://smartwp.com)

[4] [https://theproductguy.in](https://theproductguy.in)

[5] [https://www.codeant.ai](https://www.codeant.ai)

[6] [https://chetnakhanna.medium.com](https://chetnakhanna.medium.com)

[7] [https://medium.com](https://medium.com)

[8] [https://www.reddit.com](https://www.reddit.com)

[9] [https://developer.mozilla.org](https://developer.mozilla.org)

[10] [https://www.ituonline.com](https://www.ituonline.com)

[11] [https://michaellinus.medium.com](https://michaellinus.medium.com)

[12] [https://python.plainenglish.io](https://python.plainenglish.io)

[13] [https://smartwp.com](https://smartwp.com)

[14] [https://medium.com](https://medium.com)

[15] [https://www.pluralsight.com](https://www.pluralsight.com)

[16] [https://www.reddit.com](https://www.reddit.com)