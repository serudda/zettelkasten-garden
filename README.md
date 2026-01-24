# Zettelkasten Garden 🪴

A generative knowledge management system (Second Brain) based on Niklas Luhmann's methodology. This system eliminates the "blank page syndrome" by transforming writing into a process of **bottom-up assembly**.

---

## 🎯 The Goal

To move from **passive collection** to **active generation**. Every piece of information that enters the "Garden" is interrogated to find its **Core Insight**, ensuring it becomes a reusable "brick" for future content (blogs, newsletters, tweets) rather than a dead note.

## 🏛️ Methodological Pillars

| Note Type            | Source     | Purpose                                                                | Lifespan                    |
| -------------------- | ---------- | ---------------------------------------------------------------------- | --------------------------- |
| **Fleeting Notes**   | Your Brain | Quick captures of "Aha!" moments or raw thoughts.                      | Short (Process ASAP)        |
| **Literature Notes** | Others     | Summaries/quotes from external sources filtered by your understanding. | Medium (Refined into ideas) |
| **Permanent Notes**  | Synthesis  | Atomic ideas written in your own words. These are the final "assets".  | Long (Infinite)             |

## ⚙️ System Workflow: The 3-Step Refinery

The system is powered by specialized Agents and Skills that guide you through a frictionless, step-by-step conversation.

### 1. `zettelkasten-capture` (The Gatekeeper) 🟢

**Function:** Fast, low-friction entry point via `inbox.md`.

- **The Mental Hook:** Instead of complex tags, it asks for a **Core Insight** (Does this explain, challenge, or show something?).
- **Output:** Standardized English Markdown blocks with unique IDs (`YYYYMMDDHHMM`).

### 2. `zettelkasten-distill` (The Refinery) 🟡

**Function:** Linear, one-by-one processing of the `inbox.md`.

- **Transformation:** Helps you rewrite raw insights into "Permanent Notes" using your own voice and reflections.
- **Organization:** Automatically moves literature references to `/references/` and saves your unique thoughts to `/permanent/`.

### 3. `zettelkasten-assembler` (The Architect) 🔵

**Function:** Bottom-up content creation designed for non-writers.

- **Narrative Arcs:** Offers a "Menu of Inspiration" (Contrast, Myth-Buster, Bridge, Deep Dive) to structure your post.
- **The Glue:** Proposes logical transitions between your existing notes to create a cohesive draft without writing from scratch.

---

## 📂 File Structure

```text
zettelkasten-garden/
├── .claude/
│   └── skills/          # Logic for Capture, Distill, and Assembler agents
├── drafts/              # Final output for blogs, newsletters, and threads
├── zettelkasten/
│   ├── permanent/       # Your unique thoughts (The Primary Brain)
│   └── references/      # Bibliographic data and external sources
├── inbox.md             # Temporary landing zone for new ideas
├── tags.md              # Central registry of all tags
└── README.md
```
