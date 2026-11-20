# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Travis Polland's final project for the **AI Product Management Certification**, an online course from **Product School**. It specifies **Juno**, an AI product, through one artifact per course module (M1 to M5), which the M6 builder turns into a final presentation. The repo is hosted on the Nisus74 GitHub account.

It is Markdown only: there is no build, lint, or test tooling. GitHub renders the files directly.

The course sets the frame: **Juno PM** is an AI Associate PM for **RocketShip**, a B2B SaaS platform struggling with "signal collapse". Nothing shared so far defines signal collapse or who at RocketShip Juno serves, and the README pitch line is still a placeholder. Everything beyond that frame (what Juno does on its own, its human handoffs, how success is judged) is decided by Travis in class, so ask rather than invent it.

## Local course context (`docs/`)

`docs/` holds Product School course material and Travis's own notes. It is **gitignored and exists only on this machine**, so it won't appear on GitHub or in a fresh clone. Read it for context (module instructions, tool guidance, rubrics) before writing an artifact. Never copy course material into the tracked module files, and don't move anything out of `docs/` into the repo without asking.

## How artifacts get written

Each module file is a template that gets **replaced, not edited**. Every lab has a **Lab Guide** (the Product School page worked in during class) that hosts that module's named tool (M1 Skill File Builder, M3 Harness Architecture Decider and AI PRD Builder, M4 Agent Control Panel, M5 Human Evaluation Rubric). Its markdown output is copied or downloaded over the template, then committed. The blockquote at the top of each file names its tool. M2's prototype is built in an external vibe-coding tool, with screenshots of the core interaction.

- **Paths and headings are load-bearing.** In M6, the **Final Project Deliverables Builder** reads these files to generate `final-presentation.html`. Don't rename files or folders, and keep each file's heading structure intact.
- **M1 bar.** The skill file's Constraints section needs three or more guardrails, including at least one hard refusal (stricter than the template's hint).
- **M6** assembles the five deliverables plus a reflection on the course. Submission is the repo URL plus the presentation (GitHub Pages link or the file).
- **Pre-reads.** Each module has a pre-read, which also names any extra tool to sign up for. Check `docs/course/` for it before working on a module. The class schedule (Dec 2026) is in `docs/course/00-overview.md`.
- **Unfilled sections** are marked with `_____`, `_(missing)_`, or italic prompt text such as `_The one job Juno owns end-to-end._`.
- **`final-presentation.html`** is listed in the README but does not exist yet. It comes from the external builder and gets committed afterwards; don't create it by hand.
- The README's intended cadence is to commit one module's artifact per session.

## How the artifacts connect

The modules build on each other and share vocabulary, so a change in one file often implies a change in another:

- **The six harness surfaces** (01 Context, 02 Tools, 03 Loop, 04 Memory, 05 Permissions, 06 Verification) are defined in `03-harness-prd/prd.md`. The M4 Agent Control Panel's four levers are each tagged with the surface they act on: Stop Conditions (Loop), Structured Tool Outputs (Tools), Confidence Thresholds (Verification), North Star (Context).
- **Side-effect classes** `read / draft / write / send` must stay consistent across the PRD's tool verb list (02 Tools), the PRD's permissions tier table (05 Permissions, tiers `auto / confirm / blocked`), and M4's Agency Permission and Access Control rules.
- **The PRD's "Eval plan" section** is a stub that Module 5 fills: it should point to `05-evals/human-rubric.md` and its pass bar.
- **The PRD's "Out of scope" section** is derived, not free-form: anything missing from the verb list plus any action tiered `blocked`.
- **The M1 skill file** (Role, Task, Constraints, Format) defines Juno's core behaviour that the prototype (M2) and PRD (M3) should agree with.
