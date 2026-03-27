# Contributing to Markup-Driven Pronunciation Project

Thank you for your interest in contributing to this project.

This repository is a hackathon-oriented proof of concept focused on improving spoken output in assistive technology by exploring how NVDA can use author-supplied `data-ssml` metadata in educational and assessment content.

## What kinds of contributions are welcome

Contributions are welcome in several areas, including:

- documentation and editing;
- examples and sample HTML or QTI content;
- test data and expected behavior definitions;
- research questions and technical investigation;
- issue triage and refinement;
- prototype implementation work related to `sub`, `break`, `prosody`, `say-as`, and `phoneme`.

If you are not sure where to begin, documentation, examples, research questions, and clearly scoped starter tasks are all good places to start.

## Before you start

Please read these files first if they are available in the repository:

- `README.md`
- `PROJECT.md`
- `docs/open-questions.md`
- any open issues labeled for hackathon or starter work

These materials explain the project goals, technical direction, and areas where contributor help is most useful.

## Preferred contribution flow

For most non-trivial work, please open or comment on an issue before starting implementation.

This helps avoid duplicate work and makes it easier to coordinate design questions, especially for architecture, NVDA integration details, browser-to-AT bridging questions, and expected behavior for pronunciation features.

Small fixes such as wording improvements, typo corrections, or minor documentation clarifications can usually be submitted directly.

## Issues

When opening an issue, please include as much of the following as you can:

- a clear title;
- a short description of the problem, question, or proposed improvement;
- relevant examples or sample content;
- expected spoken behavior, if applicable;
- actual observed behavior, if applicable;
- environment details if the issue is technical, such as browser, NVDA version, and synthesizer;
- links to related files, specifications, or prior discussion.

Useful issue types include:

- bug report
- feature request
- research question
- hackathon task or work item
- documentation improvement

## Pull requests

When submitting a pull request, please include:

- a brief summary of what changed;
- the issue number, if there is one;
- the reason for the change;
- notes about how the change was reviewed or tested;
- any open questions or follow-up items.

If your pull request changes pronunciation behavior, examples, or parsing logic, it is especially helpful to describe:

- which `data-ssml` feature is affected;
- what spoken outcome is expected;
- whether visible text remains unchanged; and
- whether braille behavior remains unaffected.

## Design expectations

This project is guided by several core expectations:

- author-supplied pronunciation intent should be preserved where possible;
- spoken-output improvements should not require changes to visible text;
- braille behavior should not be harmed;
- standards-based and interoperable approaches are preferred.

## Scope reminders

Current work is focused on:

- NVDA 2023.1 or later;
- Chrome-based delivery environments; and
- SSML-capable synthesizers such as SAPI5 and Windows OneCore.

This repository is a proof of concept. Contributions that help clarify scope, validate assumptions, improve examples, or document open questions are valuable even when they do not result in production-ready code.

## Communication

Please keep contributions clear, respectful, and focused on helping the project move forward.

When possible, use plain language in documentation so the repository remains accessible to contributors with different backgrounds, including participants who are new to open source, accessibility engineering, or SSML.

## Thank you

Thanks for helping improve accessibility and spoken presentation for users of assistive technology.
