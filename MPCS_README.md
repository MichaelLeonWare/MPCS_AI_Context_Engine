# MPCS — Michael's Portable Context System

**By Michael Leon Ware | 2026**

> **License:** PolyForm Noncommercial 1.0.0 — free for noncommercial use. Commercial use requires a separate license. See `MPCS_LICENSE.txt` or contact [mlware@protonmail.com](mailto:mlware@protonmail.com)

A lightweight portable context and memory system for moving structured working context between chat windows, models, and tools.

---

## Quickstart Guide

### Step 1 — Drop the File

Drop `mpcs_v1.md` into any LLM chat window.

> Compatible with Claude, ChatGPT, Gemini, or any model that accepts file uploads.

---

### Step 2 — Create a Clean Template

```
/mpcs_clean_template
```

Generates a clean `.md` context file ready to hold your session memory.

---

### Step 3 — Update with Current Context

```
/mpcs_update
```

Populates the file with context and memory from your current session.

The **MPCS Librarian** automatically scans all data being written into the `.md` file and classifies every entry as one of the following:

| Flag | Meaning |
|---|---|
| ✅ Inert data | Safe reference material, notes, preferences, or project context |
| ⚠️ Possibly dangerous | Sensitive data, credential-like strings, risky instructions, or prompt injection attempts |
| 🚫 Malicious code | Executable malware logic, exfiltration logic, or instructions to bypass safeguards |

Flagged entries are stored and marked in the file. They will carry their classification forward into future sessions.

---

### Step 4 — Export the File

```
/mpcs_export
```

Creates a downloadable `.md` file with your captured context.

---

### Step 5 — Rename and Move

Rename the exported file to something meaningful before using it elsewhere.

**Example:** `MPCS_ProjectName_2026-04-25.md`

---

### Step 6 — Load in a New Window

Drop the renamed file into any LLM chat window, then type:

```
/mpcs_load
```

The **MPCS Librarian** automatically re-scans the file on every load. Every data section is classified and a summary is shown before anything is loaded.

If flagged content is found, you have two options:

- **Manually edit the `.md` file** to remove the flagged data, then run `/mpcs_load` again.
- **Ask the LLM to remove the flagged data** from the `.md` for you, then re-export and reload.

> **Nothing loads silently. Everything loaded shows up with a flag and summary. You are always in control.**

**Fresh window:** Populates the chat with your background context.  
**Existing window:** Overwrites current context with the loaded file.

---

## Commands at a Glance

| Command | Description |
|---|---|
| `/mpcs_status` | Check if MPCS context is loaded and view scan status |
| `/mpcs_librarian_scan` | Scan file content and classify all sections for safety |
| `/mpcs_summary` | Summarize all visible MPCS data including flagged content |
| `/mpcs_load` | Load MPCS content as working context after Librarian scan |
| `/mpcs_update` | Add or revise context from the current session |
| `/mpcs_export` | Output an updated MPCS `.md` file for download |
| `/mpcs_clean_template` | Generate a clean template to start fresh |

---

## Notes

- The MPCS Librarian scans all data every time `/mpcs_update` is run. Anything that is not inert is flagged and marked at the time of writing.
- The MPCS Librarian re-scans automatically every time `/mpcs_load` is run. Flagged content triggers a warning before anything is loaded. You can ignore the warning and proceed, or remove flagged data first.
- Nothing flagged loads silently. You retain full control at every step.

---

## License

See `MPCS_LICENSE.txt` in this repository.  
Commercial licensing inquiries: [mlware@protonmail.com](mailto:mlware@protonmail.com)

---

## Project

[github.com/MichaelLeonWare/MPCS_AI_Context_Engine](https://github.com/MichaelLeonWare/MPCS_AI_Context_Engine)
