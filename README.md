# Markup-Driven Pronunciation Project

Markup-Driven Pronunciation Project explores a proof of concept for improving how assistive technology speaks complex educational and assessment content. The project focuses on enabling NVDA to detect author-supplied pronunciation metadata using the 1EdTech `data-ssml` specification and pass that information to an SSML-capable speech synthesizer.

The goal is to improve pronunciation for names, acronyms, numbers, scientific terms, and other domain-specific language in a standards-based, interoperable way—without changing visible text or harming braille presentation.

## Why this matters

AT systems do not always pronounce complex or ambiguous content correctly. In educational and assessment settings, these pronunciation failures can increase cognitive load, reduce comprehension, and create accessibility barriers.

This project is intended to address that gap by exploring how open standards and open-source assistive technology can work together to support more accurate and intelligible spoken output.

## Project goals

This repository is focused on a proof of concept in which NVDA can:

- detect author-supplied `data-ssml` metadata;
- parse supported values from the 1EdTech specification;
- map those values to NVDA speech behavior; and
- pass the result to an SSML-capable speech synthesizer.

The project is designed to improve spoken output while preserving visible text and braille presentation.

## Scope

Current work is focused on:

- NVDA 2025.x or later;
- Chrome-based delivery environments; and
- SSML-capable synthesizers such as SAPI5 and Windows OneCore.

This repository is a hackathon-oriented proof of concept, not a complete platform-wide solution.

## Repository guide

- `PROJECT.md` — full technical plan
- `docs/project-scope.md` — in-scope and out-of-scope boundaries
- `docs/open-questions.md` — unresolved technical and design questions
- `docs/related-work.md` — related repositories and background
- `examples/` — sample HTML and QTI content
- `test-data/` — short phrases and expected behavior for testing
- `prototype/` or `addon/` — implementation work as it evolves


## Contribution areas

Contributors can help in several areas, including:

- documentation and editing;
- examples and sample content;
- test data and expected behavior definitions;
- issue triage and research questions; and
- prototype implementation work related to `sub`, `break`, `prosody`, `say-as`, and `phoneme`.

## Getting started

1. Read `PROJECT.md` for the technical overview.
2. Review the 1EdTech `data-ssml` specification.
3. Look through `docs/open-questions.md` and repository issues.
4. Start with documentation, examples, research questions, or clearly scoped starter tasks.

## Design principles

This project is guided by a few core principles:

- author-supplied pronunciation intent should be preserved where possible;
- improvements to spoken output should not require changes to visible text;
- braille behavior should not be harmed;
- standards-based and interoperable approaches are preferred.

## Current implementation direction

The technical plan currently explores a baseline Chrome extension bridge together with an NVDA add-on, while also investigating longer-term approaches for more direct access to `data-ssml` metadata.

For technical details, implementation notes, and open architecture questions, see `PROJECT.md`.

## References

- 1EdTech: Support for Speech Synthesis Markup Language (SSML) Using the `data-ssml` Property — https://www.1edtech.org/standards/data-ssml
- W3C Spoken Presentation Task Force — https://www.w3.org/WAI/about/groups/task-forces/spoken-presentation/
- NVDA Developer Guide — https://www.nvaccess.org/documentation/developerGuide.html
