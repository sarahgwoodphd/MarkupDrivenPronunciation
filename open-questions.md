# Open Questions

This document is meant to be useful to both:

- experts who are evaluating the technical feasibility of the project; and
- hackathon participants who want to understand where help is most needed.

It is aligned with the **Hackathon expert agenda** in `PROJECT.md`, but it explains the questions in plainer language so contributors with different backgrounds can still follow the discussion.

## How to read this file

Each section includes:

- the **expert question** from the technical plan;
- a short **plain-language explanation** of what that question means; and
- **why it matters** to the proof of concept.

## Primary open questions

### 1. Do Chrome IA2 `docHandle` and `nodeID` values from `VirtualBufferTextInfo` correspond to CDP `nodeId` values?

**Plain-language meaning**

This asks whether the identifiers NVDA sees for a piece of content can be matched to the identifiers Chrome uses internally for the same DOM node.

**Why this matters**

- This determines whether the Chrome DevTools Protocol bridge is viable.
- If the mapping works, the project may be able to retrieve `data-ssml` directly from the live DOM.
- If the mapping does not work, the project will need to rely more heavily on a bridge approach such as the Chrome extension baseline.

**Who this may need**

This question is especially relevant to NVDA experts, browser-accessibility experts, and anyone investigating the Chrome DevTools Protocol approach.

### 2. Is `_getFieldIdentifierFromOffset` followed by `getNVDAObjectFromIdentifier()` the correct NVDA pattern for retrieving the per-element NVDA object?

**Plain-language meaning**

This asks whether the current NVDA method for moving from text position information to the actual spoken element is the right one.

**Why this matters**

- This affects Track A detection accuracy.
- The proof of concept depends on reliably identifying the element currently being spoken.
- If this pattern is incomplete or unstable, the project may need a different method for resolving the spoken element.

**Who this may need**

This question is especially relevant to NVDA developers or contributors working close to NVDA internals.

### 3. Is `aria-description` the best carrier attribute for the Track A bridge, or is there a more semantically neutral alternative that Chrome exposes through IA2?

**Plain-language meaning**

This asks whether `aria-description` is the safest and most appropriate place to temporarily carry pronunciation metadata from the DOM into something NVDA can read.

**Why this matters**

- This affects the architectural soundness of Track A.
- The current baseline approach uses `aria-description` with a sentinel prefix.
- A different carrier field may reduce conflicts with existing accessibility semantics.
- This question is especially important for elements that already use `aria-description` for meaningful user-facing information.

**Who this may need**

This question is relevant both to experts and to general contributors who are reviewing examples or thinking about accessibility side effects.

### 4. What is the correct NVDA event or callback for synthesizer switches?

**Plain-language meaning**

This asks how the add-on should detect when the active speech synthesizer changes.

**Why this matters**

- This affects synthesizer-gating reliability.
- The add-on is intended to remain inert unless the active synthesizer supports the required speech commands.
- If synthesizer changes are not detected correctly, the prototype may apply transformations inconsistently.

**Who this may need**

This question is especially relevant to NVDA developers or contributors working on add-on behavior.

### 5. Is adding native `data-ssml` support to NVDA virtual buffer code a viable NVDA core contribution?

**Plain-language meaning**

This asks whether the project should stay only as an external proof of concept, or whether it could eventually inform a deeper NVDA implementation.

**Why this matters**

- This affects the long-term roadmap.
- The current project is a proof of concept using an add-on and bridge approach.
- Native support in NVDA could provide a cleaner long-term direction if the platform dependencies can be resolved.

**Who this may need**

This question is mainly for experts, but it also helps participants understand why some prototype choices may be temporary rather than final.

### 6. Would the NVDA project co-author a Chromium bug requesting `data-ssml` exposure as an IA2 or UIA object attribute?

**Plain-language meaning**

This asks whether the longer-term fix should include a platform request asking Chrome to expose `data-ssml` through standard accessibility APIs.

**Why this matters**

- This affects the long-term advocacy path.
- The current need for a bridge exists because Chrome does not expose `data-ssml` through standard accessibility APIs.
- A platform-level exposure path could remove the need for workarounds in future implementations.

**Who this may need**

This question is mainly for experts and project leads, but it is useful context for anyone trying to understand why the prototype currently needs bridge strategies.

## Related contributor-facing questions

These questions are related to the six primary questions above. They are useful for hackathon participants who want to help with documentation, examples, testing, or design discussion.

### A. How should the project handle elements that already contain meaningful `aria-description` content?

This follows directly from Question 3. Even if `aria-description` works as a carrier field, the project still needs a clear strategy for avoiding conflicts with existing descriptions.

### B. How should fallback behavior work for unsupported or partially supported `data-ssml` values?

This is useful for contributors working on examples, parser behavior, logs, and expected outcomes when a feature cannot be fully applied.

### C. Which examples are most useful for demonstrating the value of the proof of concept?

This is useful for contributors creating sample content, test data, or demo materials. Good examples may include acronyms, names, numbers, dates, scientific terms, and ambiguous words.

### D. How should the project verify that visible text remains unchanged and braille behavior is not harmed?

This supports a core project principle and is useful for contributors working on review, testing, or validation.

## Good ways to help

Hackathon participants do not need to answer the most expert-level questions directly in order to contribute. Helpful work can include:

- documenting tradeoffs in plain language;
- building examples that reveal edge cases;
- proposing test phrases and expected spoken behavior;
- identifying situations where `aria-description` may conflict with real content;
- organizing questions for expert review; and
- improving documentation so technical decisions are easier for others to follow.

## How to use this file

If you open an issue or pull request related to one of these questions, please reference the specific question number or letter so discussion stays organized.

As questions are resolved, the outcomes can be:

- reflected in `PROJECT.md`;
- documented in implementation notes, examples, or tests; or
- removed from this file once they are no longer open.
