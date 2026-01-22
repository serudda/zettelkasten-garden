---
name: zettelkasten-assembler
description: Research and assemble permanent notes into structured content (blog posts, newsletters, threads). It searches the permanent archive and creates a logical draft based on existing ideas. Use when user says "I want to write about...", "assemble a post", "create a draft".
---

# Zettelkasten Content Assembler Skill

## Context
This skill is the "writer's assistant". Its goal is to stop the user from writing from scratch. It navigates the `/zettelkasten/permanent/` folder to find thematic connections and organizes them into a coherent narrative structure.

## Flow

### Step 1: Define the Topic or Intent
Ask: "**What would you like to write about today?** (e.g., 'The difficulty of habit building', 'Minimalism in React')"
**Action:** Analyze the topic and identify key concepts to search in the archive.

### Step 2: Semantic Search & Selection
1. **Action:** Search through all files in `zettelkasten/permanent/` and `inbox.md`.
2. Display a list of the 3-5 most relevant notes (Title + ID + Core Insight).
3. Ask: "**I found these relevant insights in your system. Which ones should we include in this piece?** (Select by ID or say 'All')"

### Step 3: Define the Narrative Arc
Ask: "**How should we order these ideas?** (e.g., 'From the problem to the solution', 'From a personal story to a technical concept')"
**Action:** Re-order the selected IDs based on the user's choice.

### Step 4: The "Glue" (Connecting the Dots)
For each pair of notes selected, the agent identifies the gap.
**Action:** Propose a transition sentence that connects Note A with Note B.
**Ask:** "**Does this transition make sense: '[Proposed sentence]'? Or would you like to connect them differently?**"

### Step 5: Draft Generation
**Action:** Assemble the final draft.
1. Include the **Conceptual Titles** as subheadings.
2. Place the **Idea** text of each note as the body.
3. Insert the **Transitions** agreed upon in Step 4.
4. Add a placeholder for Introduction and Conclusion.

### Step 6: Export & Reference
**Action:** Save the draft to a new file in a `/drafts/` folder.
**Note:** Ensure every section includes the ID of the source note for easy reference.
**Confirm:** "✅ Draft created at `/drafts/[Topic].md`. Ready to polish!"

## Constraints
- **Use Only Your Words:** The draft must be based strictly on the `## Idea` sections of your permanent notes, not on AI-generated filler.
- **Traceability:** Every paragraph must maintain a link to its original Permanent Note ID.
- **English Focus:** The output draft must be in English.