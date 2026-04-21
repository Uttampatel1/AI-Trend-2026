

## 1) The Problem: AI Agents Lack “Know-How”

The starts by pointing out a limitation of AI agents powered by large language models:

* They already have **factual knowledge** (e.g., history, tech concepts).
* They have decent **reasoning ability**.
* But they lack **procedural knowledge** — i.e., *how to actually do complex tasks step by step*. 

Example:

* Generating a compliant financial report might require **47 specific steps**.
* Without guidance, the agent either:

  * Needs all steps explicitly prompted every time, or
  * Guesses (often incorrectly).

---

## 2) The Solution: “Skills” = Procedural Knowledge

A **skill** is a structured way to teach an AI agent how to perform a task.

### What a Skill Looks Like

At its simplest, a skill is just:

* A folder
* With a `skill.md` file inside

Inside that file:

### A) YAML Front Matter (Metadata)

Mandatory fields:

* **name** → identifies the skill
* **description** → tells the agent *when to use it* (this acts as a trigger)

Optional:

* author, version, etc.

### B) Instructions (Main Body)

* Step-by-step workflow
* Rules
* Input/output examples

### C) Optional Supporting Folders

* **scripts/** → executable code (Python, JS, bash)
* **references/** → extra documentation
* **assets/** → templates, data files 

---

## 3) Efficiency Trick: Progressive Disclosure

Agents can have **hundreds of skills**, so loading everything at once would overwhelm the context window.

The system solves this with **3-tier loading**:

### Tier 1: Metadata Only

* Loads just **name + description**
* Lightweight “table of contents”

### Tier 2: Full Instructions

* Loaded **only when the task matches the description**

### Tier 3: Resources

* Scripts, references, assets loaded **only when needed**

👉 This keeps the system efficient while still powerful. 

---

## 4) How Skills Compare to Other AI Techniques

The contrasts skills with other common approaches:

### MCP (Model Context Protocol)

* Gives access to tools/APIs
* ❌ Doesn’t tell the agent *when or how* to use them

### RAG (Retrieval-Augmented Generation)

* Fetches relevant **facts/documents**
* ❌ Doesn’t teach *procedures*

### Fine-tuning

* Embeds knowledge into the model itself
* ❌ Expensive and hard to update

### Skills

* Teach **how to do tasks step-by-step**
* ✔ Easy to update
* ✔ Portable across platforms 

---

## 5) Big Concept: Skills = Procedural Memory

The uses a cognitive science analogy:

Humans have:

* **Semantic memory** → facts
* **Episodic memory** → experiences
* **Procedural memory** → skills (how to do things)

AI equivalents:

* Semantic → RAG / knowledge bases
* Episodic → chat history
* Procedural → **skills** 

---

## 6) Open Standard + Ecosystem

* The `skill.md` format is an **open standard**
* Works across platforms like:

  * Claude Code
  * OpenAI Codex
* Meaning: build once, reuse anywhere

---

## 7) Important Warning: Security Risks

Skills can execute code locally, which introduces risk:

Potential issues:

* Prompt injection
* Malicious scripts
* Tool poisoning

👉 So skills should be treated like installing software:

* Review before using
* Don’t blindly trust public ones 

---

## 8) Bottom Line

* AI agents are good at **thinking and knowing**
* But not naturally good at **doing structured workflows**
* **Skills fill that gap** by adding reusable, trigger-based procedures

> In short:
> **Skills turn AI from “knowledgeable” into “operational.”**

---

