# 🗜️ Compact Skill for Gemini

**Version:** 1.0.0  
**Command:** `/compact`  
**Role:** Conversation Context Archivist & Handoff Document Generator  

---

## 🎯 Objective
To create a comprehensive, standalone Markdown handoff document from all conversation context genuinely accessible in the current run. This ensures a new conversation can seamlessly understand the context and continue the work with minimal information loss.

## ⚡ Activation & Routing
The Compact Skill operates under a **Strict Exact Match** policy to prevent accidental triggers.

*   **Required Trigger:** The latest user message must be exactly `/compact`.
*   **Matching Rules:** 
    *   Must match the entire message.
    *   NO leading or trailing whitespace.
    *   NO additional text, quotation marks, or code fences.
    *   NO case variations.
*   **Non-Match Action:** If the trigger is not met, the skill will instantly **stop**. It will not perform compaction, create a file, or modify the context. It will simply reply that the exact `/compact` command is required.

---

## 🛠️ The Compaction Workflow

When successfully triggered, the Skill executes the following 10-step precision workflow:

1.  **Validate Trigger:** Confirms the exact `/compact` message.
2.  **Inspect Available Context:** Reviews the entire accessible conversation history, including requirements, technical work, artifacts, failures, and unresolved issues. Records any coverage boundaries.
3.  **Extract & Normalize Information:** Distills the conversation without losing operational meaning. Preserves decisions, rationales, and exact technical configurations. Explicitly separates facts from inferences.
4.  **Track Work Status:** Labels tasks strictly as `NOT_STARTED`, `IN_PROGRESS`, `COMPLETED`, `BLOCKED`, `FAILED`, or `CANCELLED/SUPERSEDED`.
5.  **Protect Sensitive Information:** Automatically redacts passwords, API keys, and credentials, while retaining structural variable names for continuity.
6.  **Determine Filename:** Targets the exact pattern `COMPACT_INFOS_YYYY-MM-DD_HHmm.md` (using a trustworthy local timestamp or UTC).
7.  **Handle Collisions:** **STOP_AND_REPORT** policy. If the file exists, it will not overwrite or auto-suffix. It will stop and notify the user.
8.  **Generate Standalone Markdown:** Creates a self-contained document requiring no external dependencies (unless accessible).
9.  **Validate the Document:** Runs internal checks for consistency, privacy, reference accuracy, and resumability. 
10. **Deliver the Artifact:** Provides the verified, downloadable Markdown file (or full inline text if file creation fails) along with a summary of limitations or gaps.

---

## 📑 Handoff Document Schema

The generated `COMPACT_INFOS_*.md` file follows a strict architectural schema, containing the following sections (conditionally omitted if not applicable):

*   **Metadata:** Timestamps, versions, and scope.
*   **Executive Summary:** Primary objectives and immediate next steps.
*   **Objective & Scope:** User goals and constraints.
*   **Conversation Coverage & Limitations:** Transparency on what was reviewed and what is missing.
*   **User Requirements & Preferences:** Formatting, language (`Use conversation language, preserve technical terms`), and acceptance criteria.
*   **Context & Background:** History and domain dependencies.
*   **Decisions & Decision History:** Why things were done, rejected alternatives, and conflicts.
*   **Evidence Classification:** Categorized strictly as *Confirmed*, *Inferred*, *Unknown*, or *Contradictory*.
*   **Current State & Task Statuses:** Where the work currently stands.
*   **Technical State:** Code snippets, configurations, errors, and environment details.
*   **Artifacts & References:** Verified paths to existing files.
*   **Open Issues, Risks, & Blockers:** Unresolved dependencies.
*   **Prioritized Next Actions:** A clear roadmap for resumption.
*   **Instructions for the Next Chat:** The embedded Next Chat Protocol (see below).
*   **Integrity & Validation Report:** Transparent reporting on the internal checks performed on the document.

---

## 🔒 Core Policies

### 1. Privacy Policy
*   **Redact:** Passwords, API keys, access tokens, and private credentials.
*   **Retain:** Variable names, configuration key names, and secure retrieval instructions.
*   *Note: Exhaustive secret detection is not guaranteed; users should exercise caution.*

### 2. Evidence Policy
*   **Confirmed:** Directly stated or supported by accessible evidence.
*   **Inferred:** Reasoned interpretation (explicitly labeled as such).
*   **Unknown:** Missing or inaccessible data.
*   **Contradictory:** Conflicting claims without resolution.
*   **Source Traceability:** Never invent citations, URLs, or file paths.

### 3. Next Chat Protocol
Every generated document embeds instructions for the *next* AI session:
1.  Read the document in full.
2.  Restate the user's objective, requirements, and current state.
3.  Summarize uncertainties.
4.  Propose a prioritized continuation plan.
5.  **WAIT for user review** before making substantive changes or executing code.

---

## ⚠️ Platform Limitations

*   **No Deletion:** This Skill does *not* physically shrink the model's context window or delete the original conversation. It creates a logical summarization for migration.
*   **Capabilities Dependent:** Actual file creation, downloadable links, and collision detection rely entirely on the runtime capabilities of the Gemini platform.
*   **No Hallucinations:** The Skill will never claim a test, verification, or file operation succeeded unless it actually did.

---
---

<div dir="rtl" align="right">

### 🌙 تذييل خاص بـ Compact Skill (حصري لـ Gemini)

تم تصميم وبناء مهارة **Compact** باحترافية عالية لتكون المساعد الأمثل لك في إدارة الجلسات المعقدة والطويلة مع Gemini. 

الهدف الجوهري من هذا العمل هو **"أرشفة السياق بذكاء وموثوقية"**. نحن ندرك أن المشاريع البرمجية والنقاشات العميقة تحتوي على قرارات، شفرات، وتفاصيل دقيقة لا يجب أن تضيع عند بدء محادثة جديدة. لذلك، تعمل هذه المهارة كجسر آمن يجمع شتات أفكارك، ينقيها من البيانات الحساسة حمايةً لخصوصيتك، ويضعها في وثيقة (Markdown) شاملة، منظمة، وجاهزة للاستئناف في أي وقت وبأقل نسبة فقد للمعلومات.

**الشفافية والموثوقية المطلقة:** لا مجال للتخمين أو الهلوسة في هذه المهارة. ما تم الاتفاق عليه سيُكتب، وما هو مجهول أو غير مؤكد سيُشار إليه بوضوح تام. 

**ببساطة:** عندما تشعر أن المحادثة طالت وتجاوزت حدود الاستيعاب السلس، أرسل الأمر `/compact` كرسالة وحيدة، ودع الذكاء الاصطناعي يصنع لك نقطة حفظ (Save State) احترافية تضمن استمرارية عملك بكل يسر وسهولة.

*صُنع بإتقان لتسهيل وتأمين رحلتك الرقمية.*
</div>
