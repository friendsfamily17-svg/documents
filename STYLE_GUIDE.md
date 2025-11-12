# Documentation Style Guide

Short description
-----------------
This guide explains tone, markdown conventions, heading hierarchy, emoji usage, and linking rules for this repository. Follow these to keep documentation consistent and friendly.

## Tone

- Warm and encouraging: write like you're helping a new intern. Use "you" and short sentences.
- Practical: prefer examples and commands over abstract definitions.

## Headings

- Use `##` for top-level sections, `###` for subsections and `####` for small sub‑items.
- Keep headings descriptive and short.

## Markdown conventions

- Use fenced code blocks for commands (```bash) and short inline code with backticks for filenames or commands.
- Keep lines <= 100 characters where practical.
- Use bullet lists for steps and checklists for action items.

## File & section names

- Filenames: use kebab-case (e.g., `setup.md`, `common-errors.md`).
- Section labels: prefer clear titles like "Getting started", "Common issues", "How it’s used".

## Emoji usage

- Use a small number of emojis for clarity only (e.g., ✅ for checklists, 🧭 for guidance, 🧪 for tests). Don't overuse them.

## Internal linking

- Link to files using relative paths (e.g., `startup-dev-guides/docs/flutter/PROCESS.md`).
- When linking to headings in the same repo use lowercase hyphenated anchors (e.g., `#getting-started`).

## Examples & snippets

- Provide one short real-world example or scenario per major concept.
- Include copy-pasteable commands and mark required environment variables.

## Accessibility & clarity

- Prefer meaningful alt text for images/diagrams.
- Avoid jargon without explanation — link to definitions when needed.

## Review checklist (before merging)

- Accurate instructions and working commands.
- Followed the tone and heading rules.
- All internal links resolve.
- No large blocks of unformatted text — split into lists or subsections.
