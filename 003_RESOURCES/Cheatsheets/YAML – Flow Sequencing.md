---
oct.type: w0qat0kve8czsly6xhf2pqbh
uuid: ''
function: reference
status: current
topics:
  - yaml
  - flow-sequencing
  - language-formatting
  - knowledge-management
updated: '2026-09-02'
references:
  - https://yaml.org/spec/1.2.2/
  - >-
    https://dev.to/playfulprogramming/yaml-collections-sequences-and-mappings-4meb
  - >-
    https://docs.google.com/document/d/1Vco-fiCtWegAN7xqXjm2vm1PviEie2lBB-vWiwGKfuE/edit?usp=sharing
attribution:
  - Google Gemini
Created: '2026-09-04'
id: b4e82f3a-91c7-4d29-a5f6-8e3d2c1b9a47
---





























# YAML – Flow Sequencing

> [!INFO]
> Notes for quick reference on how to use YAML flow sequencing to keep frontmatter blocks visually cleaner and help prevent them from taking up excessive page height.

## Via Google Chrome AI Mode Search

YAML flow formatting **uses explicit symbols like brackets and braces on a single line instead of indentation to structure data**.

> As noted in the [**~YAML Spec~**](https://yaml.org/spec/1.2.2/), *“YAML also has flow styles, using explicit indicators rather than indentation to denote scope.”*

### Flow Sequences

- Use square brackets for lists.
- Separate items with commas.

> As explained by [**~DEV Community~**](https://dev.to/playfulprogramming/yaml-collections-sequences-and-mappings-4meb), *“A flow sequence is a series of YAML nodes contained in square brackets ( [ and ] ).”*

- Example: `fruits: [apple, banana, orange]`

### Flow Mappings

- Use curly braces for key-value pairs.
- Separate pairs with commas.
- Example: `user: {name: John, age: 30}`

### Key Rules

- Keep short structures on one line for readability.
- Add quotes around strings if they contain special characters like commas, brackets, or colons.

> [!TIP]
> **Gemini**: Would you like an example of mixing block and flow styles, or do you need help with **quoting special characters**inside flow collections?

> [!SUCCESS]
> **My answer**: Yes, show complex example with mixed styles.

> [!TIP]
> **Gemini**: Here is a complex example that mixes standard block style (using indentation) with flow style (using explicit brackets and braces). This technique is highly effective for keeping dense or nested data compact.
>
> ⬇︎ *Rest of note is transcript.* ⬇︎

## **Example: E-Commerce Order Data**

```yaml
order_id: "ORD-98765"
customer: { id: 1042, tier: "Premium", active: true }  # Flow mapping
shipping_address:
  street: "123 Main St"
  city: "Austin"
  state: "TX"
items:                                                  # Mixed block list with flow mappings
  - { sku: "BK-01", qty: 2, price: 15.99, tags: [book, sci-fi] }
  - { sku: "TS-05", qty: 1, price: 24.50, tags: [apparel, cotton, "v-neck"] }
metadata:
  delivery_window: "9AM-5PM"
  courier_notes: ["leave on porch", "ring bell", "beware of dog"]  # Flow sequence
```

## **Key Techniques in This Example**

- **Inline Objects:** The `customer` details are contained entirely on one line using curly braces `{ }`.
- **Nested Collections:** Inside the `items` block list, each item is a flow mapping that contains its own nested flow sequence (`tags: [book, sci-fi]`).
- **Quoting Special Characters:** In the second item, `"v-neck"` is wrapped in double quotes because it contains a hyphen, which can sometimes cause parsing issues in complex structures.

---

*AI responses may include mistakes.*