# Claude-Mem

**Claude-Mem** is a persistent memory compression and retrieval system designed for long-running work in Claude Code environments. It enables durable context retention across sessions by observing tool usage, summarizing semantic intent, and selectively reinjecting relevant knowledge when needed.

The system addresses a fundamental limitation of session-based AI tooling: loss of project context once a session ends.

---

## Overview

Claude-Mem introduces a local-first memory layer that allows Claude to retain structured understanding of a project over time. Instead of relying on repeated prompts or manual summaries, the system automatically captures and compresses relevant activity into retrievable memory units.

This enables continuity across sessions while maintaining strict control over context size, relevance, and privacy.

---

## Key Features

- Persistent memory across Claude Code sessions  
- Automatic capture of tool usage and session events  
- Semantic summarization of work into compact memory units  
- Progressive disclosure to manage context injection cost  
- Natural-language search over past sessions  
- Local-only storage with full data ownership  
- Explicit privacy controls for sensitive content  
- Transparent and inspectable memory artifacts  

---

## Motivation

AI-assisted development workflows are inherently session-bound. Important architectural decisions, debugging history, and design intent are frequently lost between sessions.

Claude-Mem aims to:

- Reduce repeated explanations and prompt overhead  
- Preserve long-term project understanding  
- Enable longitudinal reasoning across evolving codebases  
- Treat context as structured infrastructure rather than ad-hoc text  

---

## System Architecture

Claude-Mem integrates into Claude Code using lifecycle hooks that observe activity at key moments.

### Core Components

| Component | Responsibility |
|---------|----------------|
| Lifecycle Hooks | Capture session and tool activity |
| Worker Service | Processes memory and exposes APIs |
| SQLite Database | Stores observations and summaries |
| Vector Search Layer | Enables semantic retrieval |
| Memory Search Skill | Natural-language query interface |
| Web Viewer | Local inspection and debugging UI |

---

## Memory Model

| Layer | Description |
|------|-------------|
| Observations | Atomic records of tool usage and events |
| Session Summaries | Compressed representations of session intent |
| Concept Tags | Semantic labels for retrieval |
| Timelines | Ordered reconstruction of project history |

---
