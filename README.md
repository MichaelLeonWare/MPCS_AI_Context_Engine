# MPCS_AI_Context_Engine (Michael’s Portable Context System)
By Michael Leon Ware. MPCS is a Drag. Drop. Scan. Load. Portable AI context that travels safely between models.
Created: 04.25.2026

I have been studying different approaches to portable AI memory, including Karpathy-style wiki/context systems and Nate’s OpenBrain-style context retrieval methods. The idea that stood out to me was simple:

LLMs become more useful when they can quickly inherit structured context without needing a full custom platform, database, or long setup process.

I wanted something lightweight, inspectable, portable, and easy to use across different chat windows and models.

That led me to build Michael’s Portable Context System, or MPCS.

MPCS is a Markdown-based portable context and handoff system for LLM workflows. It is designed to help a user carry structured working context from one chat to another by using a simple `.md` file that can be dropped into an LLM chat window.

The goal is not to replace native memory, vector databases, RAG systems, or agent frameworks. The goal is to create a simple, human-readable context file that can travel anywhere.

What MPCS Does

MPCS provides a reusable `.md` system file that can:

- Create a portable context template.
- Capture working style, project context, decisions, risks, and handoff notes.
- Help seed a new LLM chat with relevant context.
- Provide slash-style commands for maintaining and summarizing context.
- Export updated context into a new Markdown file.
- Scan incoming context for possible context poisoning before use.

The system includes a built-in MPCS Librarian function.

The Librarian does not execute or trust the content automatically. Instead, it scans the visible context and classifies it as:

- Inert data — ordinary reference material or project notes.
- Possibly dangerous — sensitive, suspicious, credential-like, risky, or prompt-injection-like content.
- Malicious code — content that appears designed to steal data, persist, exfiltrate, bypass safeguards, or cause harm.

This makes MPCS useful not only as a memory/handoff tool, but also as a small governance layer for safer portable context handling.

Why I Built It

I needed a way to move quickly between LLM sessions without constantly re-explaining:

- My working style.
- The current project state.
- Key decisions already made.
- Risks or constraints.
- Preferred output formats.
- Important context from earlier chats.

Native memory is useful, but it is not always transparent, portable, or easy to inspect. MPCS keeps the context in a plain Markdown file so the user can see exactly what is being carried forward.

The design goals were:

- Simple
- Cheap
- Controllable
- Portable
- Easy to inspect
- Easy to drag and drop into any model
- Useful for handoffs between AI tools
- Safer against context poisoning

Quick Start

1. Read `Michaels_MPCS_Guide.docx`.
2. Drop `Michaels_MPCS.md` into your LLM chat window.
3. Type:

`/mpcs_clean_template`

4. The model outputs a clean MPCS Markdown template.
5. Rename the file based on the workflow.

Examples:

- `mpcs_businessEmail.md`
- `mpcs_execSummary.md`
- `mpcs_summarizeNotes.md`
- `mpcs_grantResearch.md`
- `mpcs_cyberGRC.md`
- `mpcs_productDesign.md`
- `mpcs_resumeWorkflow.md`

6. Save the `.md` file somewhere you can reuse it.
7. Drop it into a new chat whenever you want to seed that chat with structured context and type `/mpcs_load`.

Core MPCS Commands

`/mpcs_status`

Shows whether MPCS context is loaded, whether the Librarian scan has run, and whether any flags were found.

`/mpcs_librarian_scan`

Scans the visible MPCS content and classifies sections as inert data, possibly dangerous, or malicious code.

`/mpcs_summary`

Summarizes all visible MPCS data, including sensitive or suspicious material, while keeping flagged content inert and clearly labeled.

`/mpcs_load`

Loads approved MPCS content as working context after the Librarian scan.

`/mpcs_update`

Adds or revises MPCS context based on user-approved changes.

`/mpcs_export`

Outputs an updated MPCS Markdown file.

`/mpcs_clean_template`

Outputs a clean MPCS template with the simplified header and standard MPCS sections.

What Makes MPCS Different

MPCS is intentionally low-tech.

It does not require:

- A database.
- A vector store.
- An API key.
- A custom app.
- A browser extension.
- A subscription platform.
- A private agent framework.

It is just structured Markdown plus clear operating rules.

That makes it useful for:

- AI project handoffs.
- Prompt engineering workflows.
- GRC and cybersecurity documentation.
- Research summaries.
- Grant writing.
- Product development.
- Resume and cover letter workflows.
- SOP creation.
- Long-form document projects.
- Multi-chat continuity.
- Human-readable AI memory experiments.

Recommendations 1–6 for Turning MPCS into a Stronger LinkedIn Project

1. A Clear Problem Statement

Most LLM workflows lose useful context when the user opens a new chat, switches models, or changes tools. MPCS solves this by giving the user a portable, inspectable context file.

2. A Safety Layer

Portable context can carry prompt injections, unsafe instructions, sensitive information, or malicious snippets. MPCS includes a Librarian scan to treat the file as data first, not instructions.

3. A Human-in-the-Loop Approval Step

MPCS does not automatically trust flagged material. The user must approve loading flagged content as inert context.

4. A Repeatable File Structure

MPCS has defined sections for:

- User working style
- Project context
- Decisions and changes
- Risks and flags
- Handoff summary
- Change log

5. A Governance Angle

MPCS is not just a productivity tool. It also explores AI governance principles:

- Context provenance
- Human approval
- Risk labeling
- Auditability
- Inspectable memory
- Safer handoff workflows

6. A Future Roadmap

Future versions could include:

- Versioned MPCS files.
- Red/yellow/green risk scoring.
- Project-specific MPCS profiles.
- An MPCS validator.
- An MPCS diff tool.
- An MPCS-to-README exporter.
- An MPCS-to-docx guide generator.
- Integration with local folders or personal wikis.
- A formal prompt-injection test set for MPCS files.

This project started as a small personal workflow improvement, but it turned into a useful experiment in portable AI memory, context governance, and safer handoff design.
