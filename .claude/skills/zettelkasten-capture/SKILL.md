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

Ask: "**What type of note is this?**"

```
A) Literature Note (idea from an external source)
B) Fleeting Note (your own idea)
```

**Logic:** If 'A' → proceed to Step 3. If 'B' → skip to Step 5.

### Step 3: Identify Author and Source

Ask: "**Who is the author and what is the source?** (Book, URL, Tweet, or 'unknown')"
**Action:** Store these for the `Source:` field in the metadata.

### Step 4: Extract Key Quote (Optional for Literature)

Ask: "**Keep the exact quote? (Yes = keep it verbatim, No = write your own summary)**"
**Logic:** If 'Yes' → keep the original quote verbatim. If 'No' → ask the user for their own summary.

### Step 5: The Mental Hook (Core Insight)

Ask: "**What is the 'so what' or main insight here? (e.g., 'It explains X', 'It challenges Y', or 'It shows how Z works')**"
**Goal:** Capture the functional value of the note so it can be retrieved by "intent" rather than just keywords.

### Step 6: Suggest Tags

1. Read `tags.md` to get all existing tags.
2. Analyze content and suggest 2-3 relevant tags from the existing list.
3. Show the remaining available tags grouped by category.
4. Ask: "**Do these tags work for you, or would you like to pick others from the list or add a new one?**"
5. If the user creates a new tag → add it to `tags.md` under the appropriate category (alphabetically sorted).

### Step 7: Finalize and Append

**Action:** 1. Generate unique ID (format: `YYYYMMDDHHMM`). 2. Construct the Markdown block with YAML Frontmatter. 3. Append the block to `inbox.md`. 4. Confirm to the user: "✅ Note saved to Inbox. ID: [ID]."

## Format for inbox.md

**Language exceptions:** The following fields preserve the user's original language (do NOT translate):

- **Generated Title** → keep the original language of the source
- **Content** → keep the original language of the source
- **Core Insight** → keep the language as dictated by the user

```markdown
## [GENERATED TITLE]

- **ID:** [YYYYMMDDHHMM]
- **Type:** [Fleeting | Literature]
- **Source:** [Author - Source]
- **Tags:** #inbox [Selected tags]

### Content

[Summary or Quote]

### Capture Context

- **Core Insight:** [Answer Step 5]
```
