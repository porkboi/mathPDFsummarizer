# Math PDF Summarizer

A Codex skill for turning math-heavy PDFs into concise Markdown summaries without dropping the notation, assumptions, equations, or main results.

This repository is a skill package, not a standalone application. It provides the instructions, template, and agent metadata needed for Codex to summarize papers, lecture notes, and technical reports into implementation-friendly notes.

## What It Does

The skill is designed for documents where generic summarization is not enough, including:

- Research papers with theorems, proofs, and derivations
- Lecture notes with dense notation
- Technical appendices with objective functions or update rules
- Algorithms that need to be reimplemented from the paper

The workflow emphasizes:

- problem setup and assumptions
- notation and symbol definitions
- theorem and proposition statements
- key equations and their roles
- derivation flow
- algorithm steps
- explicit uncertainty when extraction is noisy

## Repository Layout

- `SKILL.md`: Core skill instructions and workflow
- `references/summary-template.md`: Markdown template for the final summary
- `agents/openai.yaml`: Agent metadata and default prompt
- `LICENSE`: Repository license

## How To Use

Use this skill when the task is to summarize a linked or local PDF with substantial mathematical content.

Example prompt:

```text
Use $math-pdf-summarizer to summarize this PDF into Markdown, preserving the notation, assumptions, main results, and derivations.
```

Typical inputs:

- an HTTP(S) PDF URL
- a landing page that links to the PDF
- a local PDF path

Typical output:

- a Markdown file following the template in `references/summary-template.md`

## Output Shape

The expected summary includes:

- title and source
- short overview
- problem setup
- notation table
- core definitions
- main results
- key equations
- derivation flow
- method or algorithm steps
- assumptions, limits, and uncertainties

## Design Principles

- Preserve the paper's mathematical structure instead of flattening it into prose.
- Prefer exact notation when it matters.
- Separate confirmed extraction from inference.
- Do not invent proof steps or repair broken equations without saying so.
- Focus on the math needed to understand or implement the method.

## Intended Use Case

This skill is most useful when you need a paper summary that is accurate enough to support:

- algorithm implementation
- proof review
- literature triage
- translating a PDF into structured engineering notes

## Status

The repository currently contains the skill definition and supporting template only. There are no standalone scripts or binaries in this package.
