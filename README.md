# Zettelkasten Garden

A knowledge management system (Second Brain) based on Niklas Luhmann's Zettelkasten methodology, adapted for modern content creators in 2026. The system eliminates writing friction by transforming blog, newsletter, and post creation into an assembly process of ideas rather than writing from scratch.

## The Goal

Build a generative system—not a passive storage vault. Every piece of information entering the system goes through a **Socratic Interview** that forces connections between new information and existing knowledge or current projects.

## Methodological Pillars

The system is built on three note types with clear hierarchies:

| Note Type | Purpose | Lifespan |
|-----------|---------|----------|
| **Fleeting Notes** | Quick captures of personal thoughts or "Eureka" moments | Short—must be processed |
| **Literature Notes** | Summaries and quotes from external sources (books, articles, tweets) | Medium—represents others' knowledge filtered through my understanding |
| **Permanent Notes** | Atomic ideas written in my own words, synthesizing multiple sources | Long—the "bricks" for building articles |

## The Problem: "The Note Graveyard"

Most note-taking systems become accumulation graveyards. This system is designed to be **generative**, ensuring every input is processed, connected, and eventually transformed into output.

## System Architecture

The system operates through Agents and Skills defined in `.claude/skills/`.

### Skills Roadmap

| Skill | Status | Description |
|-------|--------|-------------|
| `zettelkasten-capture` | Planned | Step-by-step conversational flow that receives fragments, classifies them, extracts metadata, and saves via append to `inbox.md` |
| `zettelkasten-distill` | Planned | Process to review `inbox.md`, reflect on notes, and transform them into independent Permanent Note `.md` files |
| `content-assembler` | Planned | Search and connection engine to "fish" related notes for assembling content drafts |

## Implementation Requirements

### Persistence
- All data saved in local Markdown files with YAML Frontmatter
- Compatible with graph tools (Obsidian, Heptabase)

### Zero Friction
- Single question at a time interactions
- Designed for capture on-the-go

### File Structure

```
zettelkasten-garden/
├── .claude/
│   └── skills/          # Agent rules and skill definitions
├── inbox.md             # Central entry point for all captures
├── zettelkasten/        # Final directory for permanent and literature notes
└── README.md
```