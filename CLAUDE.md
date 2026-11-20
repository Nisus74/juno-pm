# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Travis Polland's final project for the **AI Product Management Certification**. It specifies **Juno**, an AI product, through one artifact per course module (M1 to M5), which the M6 builder turns into a final presentation. The repo is hosted on the Nisus74 GitHub account.

It is Markdown only: there is no build, lint, or test tooling. GitHub renders the files directly.

Juno's actual concept is not defined anywhere yet (the README pitch line is still a placeholder). Ask rather than invent what Juno does, who it serves, or any product decisions.

## How artifacts get written

Each module file is a template that gets **replaced, not edited**: the course provides a named tool per module (M1 Skill File Builder, M3 Harness Architecture Decider and AI PRD Builder, M4 Agent Control Panel, M5 Human Evaluation Rubric), and its markdown output is pasted over the template. The blockquote at the top of each file names its tool.

- **Paths and headings are load-bearing.** In M6, the **Final Project Deliverables Builder** reads these files to generate `final-presentation.html`. Don't rename files or folders, and keep each file's heading structure intact.
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
