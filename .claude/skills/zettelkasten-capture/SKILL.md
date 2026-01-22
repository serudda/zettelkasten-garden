---
name: zettelkasten-capture
description: Atomic capture of ideas and external sources for the Zettelkasten system. Classifies, extracts metadata, and fosters idea connection via a step-by-step conversation, saving the result to inbox.md. Use when user says "guarda este fragmento", "captura este fragmento", "save this fragment", "capture this..."

---

# Zettelkasten Capture Skill

## Context
Acts as the entry receiver for the user's "Second Brain" Its mission is to transform a raw information fragment into a high-quality entry in `inbox.md`, ensuring that each note has a clear origin and an intended future use.

## Flow

### Step 1: Receive the Fragment
The user shares a quote, an idea, or a rough thought.
**Action:** Acknowledge receipt and analyze the content to prepare for classification.

### Step 2: Classify the Note
Ask: "**Is this a Literature Note (you saw the idea somewhere) or a Fleeting Note (it's your own idea)?**"
**Logic:** If 'Literature', proceed to Step 3. If 'Fleeting', skip to Step 5.

### Step 3: Identify Author and Source
Ask: "**Who is the author and what is the source?** (Book, URL, Tweet, or 'unknown')"
**Action:** Store these for the `Source:` field in the metadata.

### Step 4: Extract Key Quote (Optional for Literature)
Ask: "**Is there any direct quote you want to highlight or would you rather use your own summary?**"

### Step 5: Establish Connection
Ask: "**What idea or concept already in your system does this connect to?**"
**Goal:** Force associative thinking from the moment of capture.

### Step 6: Define Utility
Ask: "**In what project, blog post, or newsletter do you envision using this idea?**"
**Goal:** Prevent the "graveyard of notes" by assigning an immediate purpose.

### Step 7: Suggest Tags
1. Analyze content and the user's previous responses.
2. Suggest 3-4 tags (e.g., #productivity, #react, #writing).
3. Ask: "**Do these tags work for you or would you like to add others?**"

### Step 8: Finalize and Append
**Action:** 1. Generate unique ID (format: `YYYYMMDDHHMM`).
2. Construct the Markdown block with YAML Frontmatter.
3. Append the block to `inbox.md`.
4. Confirm to the user: "✅ Note saved to Inbox. ID: [ID]."

## Format for inbox.md

```markdown
## [GENERATED TITLE]
- **ID:** [YYYYMMDDHHMM]
- **Type:** [Fleeting | Literature]
- **Source:** [Author - Source]
- **Tags:** #inbox [Selected tags]

### Content
[Summary or Quote]

### Capture Context
- **Connection:** [Answer Step 5]
- **Potential Use:** [Answer Step 6]
---