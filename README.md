# Agent Knowledge Base

A personal knowledge base designed for AI agents.

This repository is an experiment in building a lightweight long-term memory system for AI-assisted work. It is intended to help agents such as Claude, Codex, ChatGPT, and other coding or research assistants accumulate reusable knowledge across tasks, instead of starting from scratch every time.

## Why this project exists

AI agents are becoming increasingly useful for real work: writing code, debugging projects, organizing documents, searching literature, drafting emails, and assisting with research. However, most agent workflows still have a basic limitation: the agent often lacks durable memory of the user's working habits, project structures, recurring problems, and preferred solutions.

As a result, the user may need to explain the same context repeatedly:

- how a project is organized
- which server or environment is used
- what style of writing is preferred
- what mistakes have already been made before
- which workflows are known to work
- which assumptions should be avoided

This repository is my attempt to solve that problem in a simple and transparent way.

Instead of relying only on hidden memory or conversation history, I use a structured Markdown knowledge base that an agent can read, update, and maintain during work. The goal is to make the agent gradually become more familiar with my projects, tools, and preferences through repeated use.

## What this repository is

This is not a general note-taking system.

It is a working knowledge base for agents.

The contents are meant to be practical, reusable, and task-oriented. A good note in this repository should help a future agent do something better, faster, or with fewer questions.

Examples include:

- project-specific workflows
- coding and debugging conventions
- server and environment notes
- writing preferences
- document processing workflows
- literature search strategies
- recurring mistakes and their solutions
- rules for maintaining the knowledge base itself

The repository is intentionally based on plain Markdown files. This keeps it easy to read, easy to search, easy to version control, and easy for both humans and agents to edit.

## What this repository is not

This repository is not intended to store every conversation, every temporary task, or every passing idea.

It should not become a dumping ground for raw chat logs. It should also not store sensitive credentials such as passwords, tokens, API keys, private keys, or complete login information.

The goal is to keep the knowledge base small, structured, and useful.

## Basic idea

The basic workflow is:

1. When an agent receives a task, it first checks the relevant index files.
2. If a related note exists, the agent reads it before starting the task.
3. If no related note exists, the agent proceeds normally.
4. After finishing the task, the agent decides whether something reusable was learned.
5. If so, the agent updates an existing note or creates a new one.
6. The relevant index file is updated at the same time.

In this way, the knowledge base grows gradually through actual use.

## Directory structure

```text
Agent_knowledge/
├── README.md              # Project introduction
├── index.md               # Top-level index for agents
├── Rules/                 # Rules for maintaining and using the knowledge base
├── Code/                  # Coding, debugging, environments, servers
├── Write/                 # Emails, manuscripts, slides, writing preferences
├── Document/              # Document processing, extraction, organization
└── Search/                # Search strategies, sources, verification workflows
```

Each major directory contains its own `_index.md`, which briefly describes the directory and lists the notes inside it.

## Design principles

### 1. Human-readable first

All knowledge is stored in Markdown. The files should be understandable to a human reader, not only to an agent.

### 2. Practical over complete

The repository should store information that helps future work. It does not need to be exhaustive.

### 3. Update existing notes before creating new ones

If a topic already has a note, the agent should update it instead of creating many fragmented notes.

### 4. Record decisions, not just facts

For many workflows, the most useful information is not only what was done, but why it was done that way.

### 5. Avoid sensitive information

This repository should not store secrets. If credentials are needed, the note should describe where they are managed, not reveal the credentials themselves.

### 6. Prefer stable knowledge

Temporary states, one-time tasks, and fast-changing information should generally not be stored unless they are clearly useful for future work.

## Example use cases

### Coding

An agent can learn how a project is structured, where important files are located, how to run tests, what common errors occur, and what debugging workflow is preferred.

### Writing

An agent can remember preferred wording, manuscript style, email tone, terminology choices, and expressions that should be avoided.

### Research

An agent can accumulate literature search strategies, important references, field-specific terminology, and project-specific assumptions.

### Document work

An agent can store repeatable workflows for extracting information from PDFs, organizing notes, converting formats, or preparing summaries.

### Search

An agent can maintain search strategies, useful websites, verification habits, and source-quality preferences.

## Relationship with AI agents

This project assumes that future AI agents will not only answer questions, but also participate in longer workflows. For that to work well, agents need access to stable external context.

This repository provides that context in a simple form.

It is not tied to a specific model or platform. Any agent that can read and write files can use it.

## Current status

This project is still at an early stage. The current focus is on building a clean structure, defining maintenance rules, and testing how well agents can use the knowledge base during real work.

The long-term goal is to make this repository a personal working memory layer for AI-assisted coding, writing, research, and document management.

## Maintainer

Lin Ziyang
Email: [linzy@impcas.ac.cn](mailto:linzy@impcas.ac.cn)
