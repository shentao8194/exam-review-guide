# Content and Visual Layout Standards

Use these standards when turning schedules, syllabi, lectures, notes, and past questions into exam materials. Determine scope, source roles, and deliverables from the user's current materials. Specific instructions for the current task take precedence over these defaults.

## 1. Purpose, scope, and editorial style

- Make the guide useful for exam review: cover the core material, show its hierarchy, and support recall. Merge repeated explanations, summaries, cards, and content that adds no new information.
- Set length by the completeness of core coverage and readability. Retain the concepts, mechanisms, classifications, distinctions, applications, and reasoning needed for the stated exam.
- Align framework images, detailed explanations, and questions by topic. Present the original framework image first, then its matching explanation, before moving to the next topic. Use a chapter overview for chapter-level frameworks; place topic-specific diagrams with their own content.
- Follow the agreed volume plan. If a main guide and companion volume are used, keep core explanations in the main guide and place complete practice sets or extension material in the companion volume.
- Use one column. Apply SimHei (黑体) to heading levels, SimSun (宋体) to body text, and KaiTi (楷体) to tables and their headers, typeset text and added labels in figures, captions, and supplementary content. Preserve the lettering in original handwriting and designated source screenshots. Use KaiTi for editable typeset figure text. Aim for 11–12 pt body text; review ordinary content below 10.5 pt at final page size.
- Use dotted leaders between contents entries and page numbers, then verify the final page references. Remove chapter-name suffixes that describe only a teaching format; keep parentheses that contain substantive definitions, classifications, or other knowledge.
- Write new explanations and study advice in formal, concise, positive editorial language. Convert informal advice, commands, exaggerations, and absolute experiential claims into actionable study recommendations while preserving their intended meaning. Preserve the accurate meaning of scientific conditions, limits, exceptions, negative question wording, and verbatim source passages.
- Keep original experience notes in the project audit record. Use edited formal advice in the book unless the user explicitly asks to preserve the original wording in the publication.

## 2. Match handwritten notes to explanations

### Identify the topic and crop boundary

1. Compare the source page, adjacent pages, and matching explanation to establish the topic, subtopics, and their order. Source page numbers are navigation aids; the first page in a chapter is not necessarily that chapter's overview.
2. When one page contains multiple topics, crop and place each topic separately. Read the actual content to identify continuations at the top and topic changes near the bottom.
3. Preserve the original title, necessary context, and first and last lines. If a title appears on a preceding page, add one accurate typeset title where needed. Ensure a continuation caption describes the material actually shown.
4. Place the matching detailed explanation after the image. Verify that it covers the image's key points and is supported by the sources. For similar or adjacent topics, confirm the concept, hierarchy, and chapter assignment.
5. Maintain a project mapping of topic, source and source page, crop coordinates, target heading, volume, image asset page, and final book page.

### Use only the headings the reader needs

- After technical image splitting, keep a typeset heading on the first image block for that topic. Continue adjacent fragments directly, preserving the normal reading rhythm.
- Let page headings, body hierarchy, and source content establish context across pages. Put numbering and a full caption in the first block when repeated captions would interrupt prose, tables, or connected diagrams.
- Decide whether fragments from separate source pages are continuous before adding a heading. Add a new heading for an actual topic change.
- Preserve meaningful titles, subtype names, and labels already written in the notes. Remove only redundant captions added during production.
- Check gaps, baseline spacing, and white margins between fragments. Keep scale and horizontal alignment consistent when practical; inspect joins for duplicated text, missing lines, and misaligned figures or tables.

### Improve clarity and crop safely

- Prefer original PDF images, high-resolution source images, and lossless crops. Remove genuine blank margins before sizing content for readability.
- For ghosting, faint writing, or blurred edges, use conservative contrast, denoising, or geometric correction and compare the result character by character with the source. Preserve technical glyphs, values, subscripts, superscripts, arrows, and signs. Generative redraw and unchecked OCR reflow can alter meaning.
- When scan quality cannot be reliably improved, keep the original lettering and record the limitation. Verify uncertain readings against an independent source.
- Split at semantically complete paragraph, table-row, or diagram boundaries. Keep connectors, brackets, a structural diagram, and interdependent labels together.
- Determine crop boundaries from each page's actual heading, content, and footer. A fixed crop height or repeated top/bottom cut can remove titles, final table rows, or concluding notes.
- Use hidden OCR text and PDF object bounds only to assist navigation. Confirm completeness in the final rendered image.

## 3. Verbatim material, tables, and questions

### Preserve requested source wording

- When the user requests verbatim text or tables, preserve the selected material's wording, numbers, relationships, and complete meaning. Topic selection, splitting, and layout changes must leave the passage semantically complete.
- Prefer a readable original image block. If retypesetting is necessary, proofread every word against the source. Treat OCR as a transcription draft.
- Summarize general source material when needed to keep the main guide concise. Handle content designated for verbatim preservation according to its exact wording requirement; never present a summary as a quotation.

### Tables

- Use the original table image when it is complete, clear, and readable at final size. Verify the title, headings, included rows, final row, borders, and necessary notes.
- Typeset the table when its source lettering is too small, scan quality is poor, or the original does not fit. Adjust column widths, cell padding, and item formatting while keeping body text legible.
- Keep short headers, labels, and common technical terms on one line where possible. Allow longer explanations to wrap naturally.
- Continue tables across pages at full row boundaries. Repeat essential column headings on continuation pages. Remove redundant production captions when adjacent source image fragments form one table.

### Past questions and answers

- Maintain an itemized roster of original questions, recording year, type, and source. Deduplicate exact repeats while preserving their source associations. Cover all in-scope questions across the agreed deliverables.
- The concise main guide may feature representative questions; include the remaining questions in the agreed companion volume and reconcile the full question count and unique sources.
- For unresolved-answer placeholders, verify the full question stem and the answer-key format, then consult the original key, source materials, and authoritative online references. Use the established format for single-choice, multiple-choice, and constructed-response answers.
- Prefer official standards, professional institutions, textbooks, primary literature, or other authoritative subject sources. Record links, conclusions, and relevant conditions. Document differences in date or context. Describe missing information in recalled questions precisely.
- Keep each stem before its choices. Maintain the order and association of shared case descriptions, subquestions, choices, and answers. Keep a short case set together across page breaks where possible; make continuation relationships clear for long sets.

## 4. Verification, synchronization, and cleanup

- Follow this sequence: edit the source files; compile each volume three times; render the final PDFs after compilation; review images and final page numbers; update audit notes; synchronize the PDFs and project archive. Replacing an image PDF while the compiler is reading it can produce an incomplete build or file error.
- Check fonts and missing glyphs, horizontal and vertical overflow, contents leaders and page numbers, chapter order, unique question sources, image references, and any requested closing page. Track retained image fragments separately from topic-heading count so image completeness and caption grouping are both verified.
- Render every final page, measure page occupancy, and inspect contact sheets. Review every flagged page and important image join at normal size. Flag ordinary pages with content below 60% of the available height or continuous blank space over one third of the page; record why intentional space is needed for a complete diagram, table, or case unit.
- Include the actual font setup, TeX sources, image assets, and closing-page asset if used. Compare packaged and separately delivered PDFs by hash or byte identity.
- When cleanup is authorized, preserve the latest deliverables, buildable sources, required assets, current audit notes, and synchronized project archive. Remove only covered render images, compiler intermediates, unused resources, retired scripts, and old versions. Keep original input materials separately.
- Before cleanup, verify all targets are inside the agreed project directory and all retained TeX inputs and image references resolve. Report the cleanup method accurately; emptying a recycle bin is a separate action.
