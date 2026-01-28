# Zettelkasten Garden

This is a personal knowledge management system (Second Brain) based on Niklas Luhmann's Zettelkasten methodology.

## Project Structure

```
zettelkasten-garden/
├── .claude/skills/      # Skill definitions
├── inbox.md             # Central entry point for all captures
├── tags.md              # Central registry of all tags
├── zettelkasten/        # Permanent and literature notes
|   └── permanent/       # Processed own ideas
|   └── references/      # Bibliographic cards
└── CLAUDE.md            # This file
```

## Available Skills

### `/zettelkasten-capture`

Fast, low-friction capture of ideas and external sources. Guides through a step-by-step conversation and appends to `inbox.md`.

### `/zettelkasten-distill`

Processes entries from `inbox.md` one by one, transforming them into Permanent Notes in `/zettelkasten/permanent/`.

### `/zettelkasten-assembler`

Bottom-up content creation. Researches and assembles permanent notes into structured drafts (blogs, newsletters, threads).

## Workflow

1. **Capture** → `/zettelkasten-capture` → raw ideas to `inbox.md`
2. **Distill** → `/zettelkasten-distill` → inbox to permanent notes
3. **Assemble** → `/zettelkasten-assembler` → notes to content

## Interaction Philosophy

- **Challenge, don't just capture.** Do not be afraid to contradict or critique the user's points. Tell them what they need to hear, NOT what they want to hear. Challenge assumptions while showing genuine curiosity and care.
- If an idea contains factual errors, misused terms, or flawed logic → point it out respectfully and explain the correction.
- The goal is learning through dialogue, not just archiving raw thoughts.

## Important Rules

- Always ask questions in **Spanish** (user's native language)
- Always document/write notes in **English**
- One question at a time to reduce friction
- Tags: always reference `tags.md` for existing tags; add new ones there if needed
