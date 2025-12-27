---
categories:
  - "[[notes]]"
author:
  - "[[me]]"
created: 2025-12-27
topics:
  - "[[obsidian]]"
status: done
---

This vault is an **Obsidian Vault Template** organized through **Decentralization** and **Dynamic Indexing**.

## 1. Core Design Philosophy: Everything is a Link

In this vault, **folders no longer carry classification functions**. You won't see folders like `Project/`, `Ideas/`, or `Work/`. All content files are mixed in a flat pool (`files/`).

Classification and organization rely entirely on **Wiki-Links (`[[]]`)** and **Frontmatter (YAML)**.

*   **Concept acts as Entity**: `[[AI]]` is a tag, a topic, and an actual existing file (located under `index/`).
*   **Association acts as Archiving**:
    *   **Strong Association (Topic)**: When you set `topics: [[AI]]`, you are explicitly filing the note under AI.
    *   **Weak Association (Link)**: When you mention `[[AI]]` in the text, you are creating a contextual connection.
    *   The Vault captures **BOTH** in the `index/AI.md` dashboard.

## 2. Directory Structure Analysis

The project structure is extremely streamlined, divided into "Storage Pool", "Index Layer", and "Logic Layer":

### 📂 Storage Pool (`files/`)

*   **Function**: Almost all content is here.
*   **Features**: Flat structure. Whether it's read-later articles, various notes you wrote, or project drafts, everything goes in here.
*   **Example**: `files/ai_leverage_for_knowledge.md`

### 📂 Index Layer (`index/` & `journals/`)

*   **Function**: This is your entry point and directory. Files here usually don't contain specific content but serve as a "Dynamic Viewport".
*   **Features**:
    *   `index/`: Stores all **Topics** (e.g., `AI.md`) and **Categories** (e.g., `notes.md`).
    *   `journals/`: Stores aggregations by time dimension (e.g., `2025.md`).
*   **Core Mechanism**: These files use specific templates to aggregate content:
    *   **Categories**: Aggregate by properties (Metadata).
    *   **Topics**: Aggregate by properties (Strong) AND content mentions (Weak).

### 📂 Logic Layer (`templates/bases/`)

*   **Function**: This is the "Engine" of the entire Vault. The `.base` files defined here contain the logic for querying and filtering data.
*   **Examples**:
    *   `topics.base`: "List notes where `topics` property contains *this file*".
    *   `categories.base`: "List notes where `categories` property contains *this file*".
    *   `links.base`: "List notes that mention *this file* in the body".
    *   `yearly.base`: "List notes created in the year matching *this filename*".

## 3. Advanced Dynamic Indexing Mechanism (The "Magic")

This is the most ingenious part of this template. Instead of writing repetitive query codes, this template uses **Embedded View Configurations**.

**Workflow Example:**

First, **Create Note** - You create `files/my_note.md` and add:
```yaml
topics: ["[[AI]]"]
```
Second, **View Index** - Clicking `[[AI]]` takes you to `index/AI.md`.

Third, **Dynamic Rendering** - The file `index/AI.md` uses the `index_topic_and_link_template`, which contains:
 - `![[topics.base]]`: Shows files where `topics: [[AI]]` (Strong connection).
 - `![[links.base]]`: Shows files mentioning `[[AI]]` in the body (Weak connection).

## 4. Usage Workflow Guide

### ✅ Daily Logging

1.  **New Note**: Press `Cmd/Ctrl + N`.
2.  **Select Template**:
    *   Select `note_template` for normal notes.
    *   Select `daily_template` for journals.
    *   Select `clipping_template` for excerpts.
    *   Select `post_template` for publishing drafts.
3.  **Fill Properties**:
    *   In the `topics` field, type `[[` to trigger autocomplete and link to relevant topics (e.g., `[[product_design]]`).
    *   If unsure, you can leave it blank for now.

### 🔍 Establishing New Topics

If you find yourself making many notes about "Web3":
1.  Write `[[web3]]` in any note and click to create it.
2.  Move this new file to the `index/` folder.
3.  Apply the template: `index_topic_and_link_template` 
4.  **Done!** Now `[[web3]]` is a fully functional dynamic dashboard.

### 📅 Yearly Review

1.  Open `journals/2025.md`.
2.  It automatically lists all notes in `files/` created in 2025, sorted in reverse chronological order.

## 5. Summary

This is a **"Link-Heavy, Organize-Light"** system.

*   **For the Efficient**: You don't need to struggle with "which folder should this go in" before writing. Just throw it into `files/` and use links in categories, topics, or the main text.
*   **For the Organized**: The index pages provide powerful aggregated views, allowing you to view all knowledge accumulation under a specific theme at any time.
