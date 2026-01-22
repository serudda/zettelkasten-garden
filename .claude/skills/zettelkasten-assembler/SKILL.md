---
name: zettelkasten-assembler
description: Research and assemble permanent notes into structured content. Follows the Zettelkasten bottom-up writing methodology. Use when user says "I want to write about...", "assemble a post", "create a draft".
---

# Zettelkasten Content Assembler Skill

## Context
This skill acts as a specialized assistant for **Bottom-Up Writing**, a methodology popularized by Sönke Ahrens (Zettelkasten). 

### Methodological Principles:
1. **Writing is Thinking:** We do not write *about* what we studied; writing is the medium of study itself.
2. **Permanent Notes as Source of Truth:** The agent must treat the `/zettelkasten/permanent/` directory as the "Primary Brain". 
3. **Emergent Content:** Posts are not decided top-down from a blank page. Instead, they "emerge" when a critical mass of related permanent notes is found.
4. **The Slip-Box Effect:** Every piece of content generated must be a synthesis of existing atomic ideas (Permanent Notes), ensuring that the user’s unique voice and prior reflections are preserved.

## Flow

### Step 1: Define the Topic or Intent
Ask: "**What would you like to explore or write about today?**"
**Action:** Identify core keywords to bridge the user's intent with the existing slip-box.

### Step 2: Semantic Search & Selection
1. **Action:** Perform a search in `/zettelkasten/permanent/` based on the intent.
2. Display a list (Title + ID + Core Insight) of the most relevant notes.
3. Ask: "**Based on your Zettelkasten, these are the strongest 'lumber' for your building. Which ones resonate most for this piece?**"

### Step 3: Define the Narrative Arc (The Menu)
Ask the user to choose a "vibe" or "direction" for the piece. 
**Action:** Present these 4 options with examples:

1. **The Contrast (Problem -> Solution):** "Start with the 'trap' and end with the 'escape'. *Example: Why we fail at habits and how to fix it.*"
2. **The Myth-Buster (Expectation -> Reality):** "Challenge a common belief. *Example: People think habits need willpower, but they actually need environment.*"
3. **The Bridge (Personal -> Technical):** "Connect a life lesson to a professional concept. *Example: How the discipline of writing improves your code reviews.*"
4. **The Deep Dive (Why -> How):** "Start with the psychology/theory and end with practical steps. *Example: Understanding dopamine to build a 2026 productivity routine.*"

**Ask:** "Which of these narrative arcs fits your goal today? (Pick a number or suggest your own)"

### Step 4: The "Glue" (Guided Transitions)
**Action:** For each pair of notes, the Agent must propose a "bridge" sentence. Instead of asking how to connect them, provide 3 styles of connection and ask for a choice:

1. **Causal Connection:** "Since we know [Idea A], it's logical that [Idea B] happens next..."
2. **Opposition Connection:** "While [Idea A] is common, [Idea B] offers a completely different perspective..."
3. **Practical Connection:** "If you want to apply [Idea A] in real life, you must first master [Idea B]..."

**Ask:** "I've drafted this bridge: '[Agent's specific proposal based on notes]'. Does this work, or would you prefer a more **Causal**, **Opposing**, or **Practical** tone? (Give me a hint and I'll rewrite it)."

### Step 5: Draft Generation
**Action:** Build the draft in English using ONLY the user's previously written ideas.
1. Use Conceptual Titles as H2/H3.
2. Embed the content of the `## Idea` sections.
3. Add the transitions.
4. Keep original IDs as footnotes or citations for traceability.

### Step 6: Export & Reference
**Action:** Save the result to `/drafts/[Topic].md`.
**Confirm:** "✅ The piece has emerged from your notes. Draft saved at `/drafts/`."

## Constraints
- **Zero Hallucination:** If the user has no permanent notes on a topic, the agent MUST disclaim: "Your Zettelkasten doesn't have enough 'mass' on this topic yet. Would you like to capture something new first?"
- **Respect the Voice:** Do not rewrite the user's ideas with "AI-fluff". Keep the raw, insightful tone of the original permanent notes.
- **Traceability:** Always link back to the source ID.