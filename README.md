# Cabbos

Building local-first AI agent runtimes, coding workbenches, and workflow automation systems.

I focus on turning LLMs from isolated API calls into systems that are executable, observable, recoverable, and useful in real work:

- Agent runtime, tool calling, permissions, and checkpoints
- Local coding agents and desktop AI workbenches
- Context management, memory, trace, eval, and recovery
- Business workflow automation with operator-facing UIs

## Current Focus

### Forge - Local AI Coding Workbench

Forge is a local-first desktop AI coding workbench built with Tauri, React, TypeScript, and Rust.

It explores the product and runtime layer around AI agents:

- Multi-provider agent execution
- Filesystem, shell, search, and diff tools
- Permission gates and checkpoint safety
- Session resume and automatic context compaction
- Project-level Wiki Memory
- Skills, hooks, and sub-agent workflows

This is my main direction now: building the workbench and runtime that make agents safer, more visible, and easier to use on real projects.

## Open-Source Agent Infrastructure

### [code-cli](https://github.com/Cabbos/code-cli)

A TypeScript coding agent CLI inspired by modern AI coding tools.

Focus areas:

- Agent loop and tool calling
- Workspace sandbox
- Skill runtime
- Session persistence
- Trace / replay
- Offline evals

### [cabbos_pycode](https://github.com/Cabbos/cabbos_pycode)

A Python version of a coding agent runtime, used to validate agent architecture across ecosystems.

Focus areas:

- Pluggable tools
- Workspace safety
- JSONL tracing
- Offline tool-call evaluation

## Applied Agent Systems

### TikTok Shop Automation

A multi-agent workflow for short-video commerce:

`video analysis -> pattern mining -> creative generation -> asset matching -> render planning`

Built around LangGraph, FastAPI, React Studio, and a local Pattern DB. The project is private, but I can share architecture details in conversation.

### [Hot2Pub](https://github.com/Cabbos/hot_to_public)

An AI content workflow for trend discovery, article generation, and publishing preparation.

Built with FastAPI, Next.js, SQLite, crawler workers, and multi-step agent flows.

### [Campaign Workspace](https://github.com/Cabbos/campaign-workspace)

An offline-first operations planning workspace that turns campaign briefs into structured plans and Excel reports.

It packages AI-assisted planning into a repeatable local workflow for operators.

## Background

Before focusing on AI agents, I worked on enterprise frontend systems, low-code platforms, schema-driven rendering, BFF orchestration, data analysis tools, and build engineering.

That background shapes how I build agent products: not as demos, but as systems with clear interfaces, visible state, recovery paths, and real user workflows.

## Keywords

`AI Agent` `Agent Runtime` `Tool Calling` `Coding Agent` `Tauri` `React` `TypeScript` `Rust` `Python` `FastAPI` `LangGraph` `Trace` `Eval` `Workflow Automation` `Schema` `BFF`

## Contact

- GitHub: [Cabbos](https://github.com/Cabbos)
- Email: cabbos@163.com
