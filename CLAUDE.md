# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Breakthru Beverage Group (BBG) sales management system for a Field Sales Manager overseeing a team of reps across Palm Beach County, FL. The system automates field sales workflows including rep activity tracking, supplier program management, territory performance reporting, and job search tracking.

## Architecture

### Marketplace Structure
This repo is a Cowork plugin marketplace following the [Anthropic financial-services-plugins](https://github.com/anthropics/financial-services-plugins) pattern.

- `.claude-plugin/marketplace.json` — marketplace catalog listing all plugins
- `plugins/<name>/` — each plugin is self-contained with its own manifest, skills, and commands

### Plugin Layout
Each plugin follows this structure:
```
plugins/<name>/
├── .claude-plugin/plugin.json    # Manifest (name, version, description)
├── skills/<skill-name>/SKILL.md  # Auto-triggered domain expertise
├── commands/<command>.md          # User-invoked slash commands
└── README.md
```

### Plugins
- **note-parser** — Parse rep daily reports and ride-with recaps (`/note-parser:parse-notes`, `/note-parser:recap`)
- **program-tracker** — Consolidate and track 21 supplier programs (`/program-tracker:programs`, `/program-tracker:consolidate`)
- **territory-reviews** — Weekly territory reviews and rep analysis (`/territory-reviews:weekly`, `/territory-reviews:rep-review`)
- **job-search** — Job application and follow-up tracking (`/job-search:applications`, `/job-search:follow-up`)

### Key Workflows

- **Note Parser**: Processes ride-with recaps and rep daily reports into structured data. Reps submit daily notes in varied free-text formats that need parsing into actionable items, account visits, and performance metrics.
- **Program Tracker**: Consolidates 21 supplier program formats into a unified tracking view. Each supplier (e.g., wine, spirits brands) has its own program structure, goals, and reporting format.
- **Territory Reviews**: Weekly territory performance reporting aggregating rep activity, program progress, and account-level metrics across Palm Beach County.
- **Job Search Tracker**: Tracks job applications, contacts, and follow-ups.

## Data Boundary

Company-proprietary data (account lists, pricing, distributor reports) is handled exclusively through BBG's internal AI tool (ChatGPT-4o instance). Claude Code works on tooling, parsing logic, and plugin structure — never on raw company data. Design parsers and schemas to accept data at runtime, not to embed it.

## Conventions

- Plugins follow the Anthropic financial-services-plugins directory structure and manifest format
- Prefer modular, single-purpose plugins over monolithic ones
- Schemas should accommodate the variability across 21 different supplier program formats
- Note parsing should handle free-text input from field reps (inconsistent formatting expected)
- Skills use YAML frontmatter with `description` field so Claude auto-triggers them contextually
- Commands use `argument-hint` in frontmatter when they accept arguments (e.g., `[rep-name]`)
- All paths in plugin.json must be relative to plugin root and start with `./`
- Plugins cannot reference files outside their own directory
