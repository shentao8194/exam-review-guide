---
name: exam-review-guide
description: Turn course schedules, syllabi, lectures, notes, and past exam questions into a concise, well-structured exam review guide. Use this skill to create, revise, or complete a study guide and deliver its LaTeX source and compiled PDF.
---

# Exam Review Guide

Create or maintain a printable, tablet-friendly exam review guide. Read the [production guide and prompt template](references/production-guide-and-prompt-template.md) for the project structure, LaTeX design system, examples, and compilation checks. Also read the [content and visual layout standards](references/content-and-visual-layout.md) for scope, source fidelity, image handling, question verification, and page review.

## Scope and source handling

- Determine the subject, exam scope, chapter order, question types, source roles, and deliverables from the user's materials and conversation. Ask only for information that is genuinely missing. Follow explicit scope and ordering without asking again. If a material ambiguity remains, list the alternatives and continue independent work.
- Use the official titles and sequence in the current syllabus or course schedule. Decide whether lectures, practical sessions, and labs belong in the guide from the stated exam scope. Record out-of-scope material and why it was excluded.
- Organize each topic as **framework → detailed explanation → past questions**. Use definition boxes, blue key-point bars, comparison tables, concise warnings, and memorable summaries where they improve learning.
- Keep the main guide concise while covering the concepts, mechanisms, classifications, distinctions, applications, and reasoning needed for the stated exam. Remove repeated explanations and summaries; let coverage and readability determine page count.
- Preserve user-designated verbatim supplementary material exactly, including wording, figures, and meaning. Use OCR for search and verification, then compare the selected text against the source. Write new summaries and study advice in formal, clear, positive editorial prose. Preserve the accurate meaning of scientific conditions, exceptions, negative question wording, and quoted source text.

## Typography and page design

- Use a single-column layout by default. Use SimHei for chapter, section, and other hierarchy headings; SimSun for body text; and KaiTi for tables and table headings, typeset text and labels added to figures, figure captions, and supplementary content. Retain the original lettering in handwritten notes and source screenshots. Aim for 11–12 pt body text and inspect ordinary content below 10.5 pt at page size.
- Use dotted leaders between table-of-contents entries and page numbers. Make short table headings and labels fit on one line whenever practical.
- Place each original note image immediately before the detailed explanation of its matching topic. Add a necessary caption once when a topic begins. Keep continuation images together without repeating full captions or inserting fragment numbers; add a new heading when the topic actually changes.
- Use complete, legible source tables when suitable. Otherwise typeset them with readable column widths, intact labels and rows, and clear continuation headings across pages.

## Questions and answer verification

- Inspect every supplied question source, including photographs and screenshots. Maintain a question roster with year/source, type, topic, and handling status. Compare it with questions already included and add only missing items. Preserve all in-scope questions across the agreed volumes; identify any representative-question selection when the main guide is concise.
- Check answers against supplied keys. For unresolved placeholders, verify the full stem and answer-key format, then consult reliable authoritative sources. Record the source and applicable conditions. Mark genuine uncertainty specifically; label newly written practice questions as practice.
- Keep stems, shared case descriptions, subquestions, choices, and answers together and in reading order. Preserve the original wording of past questions.

## LaTeX project and publication review

- Use a multi-file LaTeX project with `main.tex`, `preamble.tex`, `body/chN.tex`, `gen/q_chN.tex`, image assets, and a concise build guide. Keep each chapter's explanations in its body file and its questions in the corresponding question file.
- Adapt the reusable preamble in the production guide to the subject and the user's requirements. Preserve font fallbacks for special symbols. If the specified fonts are unavailable, select suitable installed fonts, document the substitution, and inspect the actual output.
- Write the book as a standalone publication. Keep local-file references, source inventories, production notes, and compilation details in project documentation rather than in the book itself. Add an ending page only when requested or supplied for the current work.
- Reflow content in reading order rather than copying entire source pages indiscriminately. Remove obsolete source page numbers, headers, footers, and decorative elements when they carry no subject information; log such cleanup and preserve all required knowledge content.
- Inspect the rendered final PDF page by page. Check image titles and boundaries, cropped content, reading order, legibility, tables, page breaks, contents leaders, page numbers, headings, isolated lines, and unusually sparse pages. Review suspected pages at normal size; a contact sheet alone is insufficient.
- Keep source assets stable during compilation and rendering. Compile with XeLaTeX or LuaLaTeX three times when the environment supports the full project. Check compiler exit status and missing-character warnings, render the final PDF, update page references in the audit notes, and synchronize the delivered PDF with the source package.
- Deliver the complete source project, compiled PDF, and build instructions. State out-of-scope exclusions, unresolved questions, font substitutions, and any verification that could not be completed. When cleanup is authorized, preserve the current buildable source, required assets, final deliverables, and current audit notes; keep original input materials separately.
