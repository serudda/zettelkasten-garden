---
name: zettelkasten-distill
description: Process entries from inbox.md one by one to transform them into Permanent Notes. It handles file creation in the Zettelkasten folder, moves literature references, and cleans up the inbox. Use when user says "process inbox", "distill my notes", "organize inbox".
---

# Zettelkasten Distillation Skill

## Context

This skill is the "refinery" of the system. It takes raw captures (Fleeting/Literature) and helps the user synthesize them into Permanent Notes. A Permanent Note is an idea written in the user's own words, designed to be understood by their "future self" without needing the original context.

## Flow

### Step 1: Scan and Select

The agent reads `inbox.md`.

- If empty: Notify the user and terminate.
- If not empty: Identify the **first** note in the file.
  **Action:** Display the note's content and Core Insight to the user.
  **Ask:** "Ready to distill this note? (Yes/Skip)"

### Step 2: Elaborate (Permanent Note Creation)

A Permanent Note must be written in the user's own words.
**Ask:** "**Based on the Core Insight, how would you explain this idea to your future self in 2-3 sentences?**"
**Goal:** Transform "someone else's idea" into "your own thought".
**Language Rule:** Preserve the user's elaboration in the original language they used. Do NOT translate it.

### Step 3: Validate & Polish Draft

**Validation Checkpoint:** Before polishing, critically review the user's elaboration:

- Does it contain factual errors or misused terms?
- Is the logic sound, or are there flawed assumptions?
- Could the idea be misunderstood by their "future self"?

**If issues are found:** Point them out respectfully. Explain the correction and ask if the user wants to revise their elaboration.

**Action:** Once validated, clean up the user's elaboration:

- Fix grammar and spelling errors
- Remove redundancies
- Add proper punctuation
- Improve coherence between sentences

**Rule:** Preserve the user's tone, voice, and original language. Do NOT rephrase or transform the idea.
**Ask:** "**Here's a polished version of your idea. Does it still capture what you meant?**"
[Show polished version]

### Step 4: Conceptual Titling

Permanent notes need a title that describes the _concept_, not the source.
**Ask:** "**What is a clear, conceptual title for this Permanent Note?** (e.g., 'The Hidden Cost of Habits' instead of 'Brian Tracy Quote')"

### Step 5: Internal Connections (The Zettelkasten Link)

Search the `/zettelkasten/permanent/` folder for existing notes.
**Action:** Suggest 2-3 existing note titles/IDs that might be related.
**Ask:** "**Does this note connect to any of these? If so, how?** (e.g., 'Builds on [[ID]]', 'Contradicts [[ID]]')"

### Step 6: Metadata & Tags Refinement

1. Read `tags.md` to get all existing tags.
2. Suggest refined tags from the existing list (remove #inbox, add more specific ones if needed).
3. Show the remaining available tags grouped by category.
4. **Ask:** "**Are these tags correct for the permanent archive, or would you like to pick others from the list or add a new one?**"
5. If the user creates a new tag → add it to `tags.md` under the appropriate category (alphabetically sorted).

### Step 7: File Generation & Inbox Cleanup

**Action:**

1. **Create Permanent Note:** Save to `zettelkasten/permanent/[ID].md` using the template below.
2. **Handle Literature (if applicable):** If it's a Literature Note, create/update a file in `zettelkasten/references/[Source_Name].md` with the bibliographic data and a link to the new Permanent Note.
3. **Delete from Inbox:** Remove ONLY this note's block from `inbox.md`.

### Step 8: Continuity Check

**Action:** Confirm the note has been archived.
**Ask:** "**Note processed and removed from Inbox. Would you like to process the next one?**"

## Output Format (Permanent Note)

```markdown
# [Conceptual Title]

- **ID:** [YYYYMMDDHHMM]
- **Date:** [Current Date]
- **Tags:** [Refined Tags]
- **Source:** [[Reference_Link]]

## Idea

[Polished elaboration from Step 3]

## Connections

- [Connection details from Step 5]

---

## Original Context

> [Original Complete content from "### Content" section]
```
