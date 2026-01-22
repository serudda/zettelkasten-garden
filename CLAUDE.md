# Zettelkasten Garden

This is a personal knowledge management system (Second Brain) based on Niklas Luhmann's Zettelkasten methodology.

## Project Structure

```
zettelkasten-garden/
├── .claude/skills/      # Skill definitions
├── inbox.md             # Central entry point for all captures
├── zettelkasten/        # Permanent and literature notes
|   └── permanent/       # Processed own ideas
|   └── references/      # Bibliographic cards
└── CLAUDE.md            # This file
```

## Available Skills

### `/zettelkasten-capture`
Atomic capture of ideas and external sources. Use this skill when the user wants to:
- Save a quote, idea, or thought
- Process raw information into the inbox
- Capture something for later distillation

The skill guides through a step-by-step conversation (one question at a time) and appends the result to `inbox.md`.

## Workflow

1. **Capture** → Use `/zettelkasten-capture` to add raw ideas to `inbox.md`
2. **Distill** → (Coming soon) Process inbox into permanent notes
3. **Assemble** → (Coming soon) Connect notes to create content

## Important Rules

- Always ask questions in **Spanish** (user's native language)
- Always document/write notes in **English**
- One question at a time to reduce friction
- Every note must have a connection and potential use defined
