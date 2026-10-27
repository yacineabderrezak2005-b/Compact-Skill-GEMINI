# 🗜️ Compact Skill for Gemini

**Version:** 1.0.0 | **Role:** Conversation Context Archivist & Handoff Document Generator

---

## 📖 Overview

The **Compact Skill** is a highly structured, precision-driven workflow designed for Gemini. Its primary objective is to create a comprehensive, standalone Markdown handoff document from your current conversation. 

When context windows get too long, or when you need to pause a complex project and resume it in a fresh chat, the Compact Skill ensures **zero information loss**. It intelligently archives user requirements, technical states, decisions, and open issues into a highly readable, resumable document.

## ✨ Key Features

*   **Strict Activation:** Triggers *only* on an exact `/compact` command, preventing accidental executions.
*   **Intelligent Extraction:** Normalizes information, preserves constraints, and explicitly separates confirmed facts from inferences or unknowns.
*   **Privacy First:** Automatically redacts passwords, API keys, and sensitive credentials while retaining structural variables needed for context.
*   **Honest Reporting:** Will not hallucinate files, dates, or rationales. If context is missing, it explicitly documents the gap.
*   **Safe File Handling:** Generates a clearly named file (`COMPACT_INFOS_YYYY-MM-DD_HHmm.md`) and actively prevents overwriting existing files (Collision Action: STOP_AND_REPORT).
*   **Next-Chat Protocol:** Embeds specific instructions inside the generated document so the *next* AI agent knows exactly how to read it, state its understanding, and await your green light before proceeding.

## 🚀 How to Use

To activate the skill, simply send the following command as your **latest and only** message:

```text
/compact
```

### ⚠️ Activation Rules
* **Exact Match Required:** The message must be *exactly* `/compact`.
* **No Extras:** Do not add leading/trailing spaces, quotation marks, or additional instructions. If the condition is not met, the skill will instantly halt.

## 📄 The Handoff Document (`COMPACT_INFOS_*.md`)

Upon successful execution, you will receive a standalone Markdown document. This document acts as your project's "save state" and includes several strictly structured sections:

1.  **Metadata & Executive Summary:** Time, status, and primary objectives.
2.  **Coverage & Limitations:** Exactly what was (and wasn't) accessible during generation.
3.  **User Requirements & Context:** Boundaries, history, and domain knowledge.
4.  **Decisions & Evidence:** Tracked changes, rejected alternatives, and confirmed/inferred data.
5.  **Technical State & Artifacts:** Relevant file paths, code snippets, versions, and configurations.
6.  **Task Statuses:** Clear labels (`IN_PROGRESS`, `BLOCKED`, `COMPLETED`).
7.  **Prioritized Next Actions:** A definitive guide on what needs to happen next.
8.  **Integrity Report:** Internal validation checks performed before delivery.

## 🔄 Resuming Your Work

1. Start a **new chat** with Gemini.
2. Upload or paste the `COMPACT_INFOS_*.md` document.
3. The embedded **Next Chat Protocol** will instruct the AI to:
   * Read the document in full.
   * Restate your goals and current status.
   * Propose a prioritized plan.
   * **Wait for your review** before executing any code or making substantive changes.

## 🛑 Limitations and Disclaimers

*   **Platform Dependency:** Actual file creation, download links, and collision detection rely on the runtime capabilities of the Gemini platform.
*   **No Deletion:** This skill does *not* physically shrink the context window or delete the original conversation; it creates a logical summary for migration.
*   **Privacy:** While secret detection is robust, it is not infallible. Always review the final document if your chat contained highly sensitive proprietary data.

---
---


### تذييل خاص بـ Compact Skill (حصري لـ Gemini)

تم تصميم وبناء مهارة **Compact** باحترافية عالية لتكون المساعد الأمثل لك في إدارة الجلسات المعقدة والطويلة مع Gemini. 

الهدف الجوهري من هذا العمل هو **"أرشفة السياق بذكاء"**. نحن ندرك أن المشاريع البرمجية والنقاشات العميقة تحتوي على قرارات، شفرات، وتفاصيل دقيقة لا يجب أن تضيع عند بدء محادثة جديدة. لذلك، تعمل هذه المهارة كجسر آمن يجمع شتات أفكارك، ينقيها من البيانات الحساسة حمايةً لخصوصيتك، ويضعها في وثيقة (Markdown) شاملة وجاهزة للاستئناف في أي وقت.

**الشفافية والموثوقية:** لا مجال للتخمين أو الهلوسة هنا. ما تم الاتفاق عليه سيُكتب، وما هو مجهول سيُشار إليه بوضوح. 

**ببساطة:** عندما تشعر أن المحادثة طالت أو تعقدت، اكتب `/compact`، ودع الذكاء الاصطناعي يصنع لك نقطة حفظ (Save State) احترافية تضمن استمرارية عملك بكل يسر وسهولة.

*صُنع بإتقان لتسهيل رحلتك الرقمية.*