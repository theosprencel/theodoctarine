---
oct.type: w0qat0kve8czsly6xhf2pqbh
id: 91e7c4a6-8d3b-4f52-a97e-6b28d1f043c5
aliases:
  - Guide to Google AI Tools
  - Find the Right Google AI Tool
Description: >-
  Gemini-created guide to Google AI tools and when to use them, with comparisons
  and contrasts.
source: Google Gemini
status: doing
tags:
  - google-gemini
  - ai-studio
  - ai-models
  - working-with-ai
created: '2026-07-24'
updated: '2026-07-24'
---

> [!INFO]
> This started as a simple question about AI Studio Build and I figured I'd turn it into a reference sheet for Google's various AI entry points and offerings.

---

## **How AI Studio Build Works**

Unlike a standard chat interface that only outputs text or copyable code blocks, **AI Studio Build** combines conversational chat with a real-time development environment:

- **Real Application Container**: A full Node.js / React / Vite environment running in Cloud Run behind the scenes.

- **Agentic Coding**: As we talk, I can inspect, edit, and create code files, install packages, handle API keys securely, and verify builds automatically.

- **Live Interactive Preview**: You see the real application updating in real time in the preview pane alongside our conversation.

**Google AI Studio Build** is a full-stack, agentic web application builder powered by Gemini models, designed specifically to turn natural language prompts into live, runnable web applications.

Here is how it compares to Gemini direct chat, Project Opal, and platforms like ChatGPT Canvas:

### **When to Use AI Studio Build vs. Gemini Directly**

| **Task** | **Where to Go** | **Why** |
| --- | --- | --- |
| **Building Web Apps, Dashboards, & Tools** | **AI Studio Build** *(Here)* | Live hosting, automatic code execution, visual editing, multi-file management, and deployment. |
| **Conversational Q&A, Writing, & General Chat** | **Gemini** *([gemini.google.com](http://gemini.google.com))* | Fast, straightforward conversational AI for text, summaries, document drafts, and general inquiries. |
| **Prompt Engineering & API Playground** | **Google AI Studio** *(Chat/Freeform Prompts)* | Fine-tuning system instructions, testing raw Gemini API parameters, temperature tuning, and evaluating models. |

---

### **1. How AI Studio Build Differs from Project Opal**

- **Project Opal** (from Google Labs) was focused on visual workflow chaining—connecting prompts, AI steps, and mini UI cards together visually to build interactive mini-tools without touching traditional code.

- **AI Studio Build** is a true **full-stack software creation environment**. An AI coding agent generates standard web code (React, TypeScript, Tailwind CSS, Express/Node.js), manages real project files and dependencies, runs a live development server in a containerized environment, and gives you a live interactive preview of the application.

---

### **2. When to Use Gemini Directly vs. AI Studio Build**

- **Use Gemini directly ([gemini.google.com](http://gemini.google.com))** for:

  - General conversation, Q&A, writing, and brainstorming.

  - Analyzing documents, summarizing text, or web search grounding.

  - Quick code snippet generation when you just want a snippet to paste elsewhere.

- **Use AI Studio Build (ai.studio/build)** for:

  - Building, testing, and iterating on functional web applications, dashboards, or tools.

  - Creating apps with persistent storage (Firebase/Cloud SQL), backend API routes, or Google Workspace integrations.

  - Previewing your app live, exporting the complete codebase to GitHub/ZIP, or deploying directly to Cloud Run.

---

### **3. Comparison to Dual Chat/Building Interfaces (e.g. ChatGPT Canvas)**

Similar to Canvas or dual-pane code builders, AI Studio Build pairs a natural language chat interface with a live preview/workspace panel.

The key distinction with AI Studio Build is that it operates on a full multi-file web project behind the scenes. You can view the code, inspect the file tree, edit specific files, add npm packages, configure environment variables, and run real server-side API endpoints (such as proxying Gemini API calls or third-party APIs).

---