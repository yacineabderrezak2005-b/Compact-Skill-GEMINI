Compact Context — Design Principles

1. Project Overview

Compact Context is an open-source project designed to preserve useful conversational context and enable reliable handoffs between AI conversations.

The project converts accessible conversation history into a structured, self-contained Markdown document that helps a new conversation understand the user's objectives, decisions, current state, constraints, and next steps.

The initial release targets Gemini, while the underlying document structure and core principles are designed to support future platform integrations.

2. Mission

Make long-running AI-assisted work easier to preserve, transfer, review, and resume without unnecessarily repeating previous context.

3. Core Principles

3.1 Context Fidelity

Preserve information that materially affects continuity, including:

- User objectives and requirements.
- Important decisions and their known rationale.
- Current project state and completed work.
- Technical details, relevant artifacts, and references.
- Open questions, blockers, risks, and dependencies.
- Prioritized next steps.

Reduce repetition without discarding operationally important information.

3.2 Evidence Transparency

Distinguish between:

- Confirmed: Explicitly stated or supported by accessible evidence.
- Inferred: Reasonably concluded but not explicitly confirmed.
- Unknown: Missing, inaccessible, or unverified information.
- Contradictory: Conflicting information that remains unresolved.

Never invent facts, decisions, test results, citations, file paths, or historical context.

3.3 Honest Coverage

Document only the conversation history and materials actually accessible to the current execution.

When information is unavailable, state the limitation and explain its potential impact on continuity.

Do not describe a partial summary as a verified, complete transcript of the original conversation.

3.4 Privacy by Default

Redact credentials, API keys, passwords, access tokens, and other sensitive values by default.

Preserve useful configuration names and explain how authorized users can retrieve sensitive values from appropriate secure sources.

Review generated documents for sensitive information before delivery. Do not claim that automated detection can identify every secret.

3.5 Operational Resumability

The handoff document must enable a new conversation to reconstruct the practical state of the work.

It should identify completed tasks, ongoing work, blockers, unresolved decisions, dependencies, and the next recommended actions.

A receiving conversation must first summarize its understanding and propose a plan for user review before making substantive changes.

3.6 Platform Honesty

Do not claim that Compact Context deletes the original conversation, reduces the model's context window, or retrieves inaccessible history.

Actual behavior depends on the capabilities and permissions of the host platform and execution environment.

3.7 Verifiable Outputs

When file creation is supported, create and verify a real Markdown artifact before providing a download link.

If file creation fails or is unavailable, provide the complete Markdown content inline and explicitly disclose that no downloadable file was created.

Report only validation checks that were actually performed.

4. Initial Scope

The initial release, "v0.1.0", focuses on:

- A Gemini-oriented "/compact" skill.
- A standalone Markdown context handoff document.
- A predictable output filename.
- Explicit evidence classification.
- Task and project status tracking.
- Privacy safeguards.
- An integrity and validation report.
- Clear documentation of platform limitations.

5. Activation Contract

The intended trigger is the exact message:

"/compact"

The command must constitute the entire latest user message, with no additional text, quotation marks, code fences, or surrounding whitespace.

If the condition is not satisfied, the skill must not perform the compaction workflow or create an output file.

This is a behavioral requirement. Guaranteed exclusive routing may require host-platform support and must not be claimed unless verified.

6. Output Contract

The intended filename pattern is:

"COMPACT_INFOS_YYYY-MM-DD_HHmm.md"

Use a trustworthy local timestamp when available. Otherwise, use UTC and record the timezone in the document.

If the exact target filename already exists and the runtime can verify this, stop without overwriting the existing file, appending a suffix, or silently changing the naming pattern.

The output must be self-contained, written in Markdown, and include an integrity and validation report.

7. Task Status Vocabulary

Use the following status values consistently:

- "NOT_STARTED"
- "IN_PROGRESS"
- "COMPLETED"
- "BLOCKED"
- "FAILED"
- "CANCELLED"
- "SUPERSEDED"

Cancellation and supersession are separate states in the documentation model, even if a combined label is used in a compact presentation.

8. Architecture Principles

Keep the project divided conceptually into:

1. Core specification: Platform-independent rules for evidence handling, document structure, privacy, and resumability.
2. Platform adapter: Platform-specific instructions, activation behavior, installation requirements, and runtime limitations.
3. Output template: The canonical structure of the generated handoff document.
4. Validation guidance: Checks and test cases for document quality and platform behavior.

The Gemini integration is the first adapter, not the definition of the entire project.

Platform-independent specifications must not assume that every host supports identical commands, permissions, file operations, or routing behavior.

9. Initial Non-Goals

The initial release does not promise:

- Guaranteed access to the complete historical conversation.
- Guaranteed exclusive command routing.
- Guaranteed file creation in every environment.
- Automatic deletion or modification of the original conversation.
- Physical reduction of the model's context window.
- Automatic synchronization across AI platforms.
- Perfect detection of all sensitive information.
- Compatibility with platforms that have not been tested.

10. Release Acceptance Criteria

The initial release is ready for publication when:

- The Gemini skill instructions are documented.
- The output format is clearly specified.
- The JSON companion and skill instructions are consistent.
- The sample document uses synthetic, non-sensitive information.
- Trigger, privacy, collision, fallback, and validation cases are documented.
- Installation and usage instructions are available.
- Known limitations are disclosed.
- The selected license is included.
- No unverified test or compatibility claims are presented as facts.

11. Project Status

Current status: Specification draft.

Next milestone: Establish the repository structure and define the authoritative source of truth for the platform instructions and JSON companion.

Publication status: No public repository or release is implied by this document.