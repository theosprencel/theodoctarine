---
oct.type: bb1wniq7295zdc49dd8k6hst
id: f66226a3-856f-41d6-8ab7-ee2a59c83eea
function: collect
status: active
topics:
  - ai-agents
  - object-oriented
  - metadata-properties
created: 2026-09-18T04:00
updated: 2026-09-18T18:34
references:
  - https://app.capacities.io/home/58bba91f-b085-42c4-b7eb-dc7cf32e3fd9
attribution:
  - Capacities AI Assistant
---



# Agents Object Type Schema

> [!INFO]
> This is the full text of the response from **Capacities AI Assistant** when I prompted it to provide properties to be added to an **Agents Object Type** in the **Capacities** app. I’ve added the information here, and in a couple other places, because I felt its value could extend beyond Capacities alone.

> **Recommended property schema for the Agents object type**
> Lead: structure for quick decision making, with clear boundaries between what belongs in properties, tags, links, and body content.

## Core properties (required or strongly recommended)

- **Provider**: text or select. Required. Examples: OpenAI, Google, Capacities, Anthropic.
- **Model / Version**: text. Required when known. Examples: GPT-4.1, Gemini 2.5 Pro, Codex.
- **Primary use cases**: multi-select. Required. Examples: Coding, research, synthesis, brainstorming, writing, automation, knowledge management.
- **Current status**: select. Recommended. Examples: Active, testing, paused, retired, unavailable.
- **Last evaluated**: date. Recommended. Helps track staleness of assessment.
- **Recommended for**: text or multi-select. Recommended. Describes where this agent is your default choice.

Optional but high leverage

- **Access / interface**: multi-select. Optional. Examples: Chat app, API, IDE, Capacities, command line, browser extension.
- **Limitations**: text. Recommended. Document known weaknesses or constraints.
- **Cost tier**: text or select. Optional. Examples: free, paid, API usage, subscription-only.
- **Latency**: select. Optional. Examples: low, medium, high.
- **Privacy / data sensitivity**: text or select. Optional. Examples: public, internal, confidential, highly sensitive.
- **Strengths**: multi-select or text. Optional. Examples: structured reasoning, code generation, long-context synthesis, tone matching.
- **Typical output quality**: rating (1–5) or text. Optional.
- **Documentation URL**: URL field. Optional. Direct access to official docs.
- **Prompt library link**: URL or reference. Optional. Link to prompts you reuse.
- **Replacement / successor**: link or reference. Optional. Points to a newer agent if applicable.

## Minimal viable schema (start small)

- Provider
- Model / Version
- Primary use cases
- Current status
- Last evaluated
- Preferred for

Add the following only if they affect choice or workflow

- Cost tier
- Latency
- Privacy / data sensitivity
- Strengths
- Limitations

## What belongs in properties versus tags, links, and body

- **Properties**: for comparative analysis and structured querying. Use properties when you want side-by-side filtering or sorting (for example, which agents support coding best, or which are active and low latency). Keep properties stable and queryable.
- **Tags**: for emergent, cross-cutting themes and discoverability. Use tags for ephemeral descriptors that do not fit strict categories, such as #opinionated or #hallucination-prone. Tags aid exploration without fragmenting the core schema.
- **Links**: for contextual relationships and provenance. Link an agent to related Projects, Notes, prompt notes, evaluations, meeting notes, or example conversations. Links create a trace of how the agent was used in practice.
- **Body**: for qualitative notes that don’t fit into structured fields. Use the body to store working instructions, comparison observations, examples of successful prompts, and a concise “how I use this” guide.

## Maintenance mindset

- The One Idea Rule: Treat each Agents object as a specific configuration or instance. If you use an agent for two very different tasks, assess whether to create separate objects or keep distinct System Prompt notes within the same object.
- Revisit as inquiry: If an agent repeatedly fails a task, inspect whether the issue is the agent itself or the System Prompt and adjust accordingly.
- Living profiles: Update the Model Version when the model updates. Use a tag like #archived to note ceased usefulness instead of deleting history.

This schema emphasizes a focused, decision-driven profile that remains lean while supporting meaningful queries and evolution over time.

---

## Addendum: Adding Role and Owner

> [!INFO]
> I followed up with Capacities AI Assistant about adding Role and Owner properties to the Agents schema, and it confirmed they would be valuable additions. What follows is the full text of the response.

> **Bottom line:** Yes, Role and Owner belong on the Agents object type, but they serve different purposes and must be modeled differently.

## Role

- **Precise meaning:** The agent’s functional responsibility or persona. It answers *who the agent is in function* rather than what work you do with it.
- **Relation to existing properties:**
  - Distinct from **Primary use cases** (which describe the work you use the agent for).
  - Distinct from **Recommended for** (which guides when to choose this agent over others).
  - In practice, Role helps you compare agents by function, while Primary use cases and Recommended for guide tasks and selection context.
- **Data type and options:**
  - **Data type:** Multi-select is the safe default, since an agent can embody multiple roles (for example, a ChatGPT/Codex instance can be both a **Coding assistant** and an **Editor**).
  - **Required:** Optional initially; consider making it required once your vocabulary stabilizes.
  - **Suggested options (high level):** General assistant, Researcher, Analyst, Writer, Editor, Tutor / explainer, Coding assistant, Reviewer / critic, Summarizer, Synthesizer, Planner, Automator, Knowledge-management assistant, Creative partner.
- **Guiding principles:**
  - Avoid overly specific role values (these belong in a project relationship or a use case rather than a general Role value).
  - Role should be kept at a level that supports comparison across agents without becoming a directory of granular tasks.
  - If Role starts mirroring Recommended for, consider the separation: Role is the *who*; Primary use case is the *what*; Recommended for is the *when/why*.

## Owner

- **Precise meaning:** Who is responsible for the agent’s maintenance, updates, prompts, or configuration integrity.
- **Two viable meanings (do not combine):**
  - Option A: Responsible person for accountability. Data type: Link to a Person object.
  - Option B: Provider / organization. Data type: Link to an Organization object, or a small fixed list if you need a simple selector.
- **Recommendation in practice:**
  - Use Owner for the responsible person only if accountability is meaningful in your system. If you already capture Provider separately, keep Owner distinct and avoid conflating the two.
  - If your catalog includes external services, Provider remains the right place for organization behind the agent; Owner covers who maintains or is answerable for the agent.
- **Data type and controls (Option A):**
  - Data type: Person link (preferred) or a simple single-select if you only need “Me,” “Team,” or “External.”
  - Required: Optional when ownership is not central; consider making it mandatory only if responsibility tracking is essential.
- **Data type and controls (Option B):**
  - Data type: Organization link or a small fixed list.
  - Required: Usually required if cataloging external services.

## Relationship to the existing fields

- **Provider** should remain as the organization behind the agent. Do not collapse Provider and Owner into a single field.
- **Current status** and **Last evaluated** are orthogonal metadata and remain unchanged in this context.
- **Primary use cases** describe the domain or tasks the agent supports; **Role** describes the agent’s functional persona; **Recommended for** conveys when to choose this agent. These are complementary and should coexist with clear distinctions.

## Final setup recommendation

- **Role:** multi-select; optional initially; controlled vocabulary with high-level values.
- **Owner:** Person link; optional unless explicit accountability is required.
- **Provider:** select or Organization link; separate from Owner.
- **Primary use cases:** multi-select; describes the work.
- **Recommended for:** text or multi-select; describes guidance for selection.
- **Current status:** select.
- **Last evaluated:** date.

One practical caution: if every Agent object is a simple model or service without separate prompts or configurations, Owner may add little value. In that case keep it optional. Role remains broadly useful because it supports comparison by function. When evaluating inclusion, test whether these properties meaningfully aid in inquiry and decision-making within your system. A property earns its place when it clarifies who to consult or which tool to reach for during a process.