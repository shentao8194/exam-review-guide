# Exam Review Guide: Production Guide and Prompt Template

Use these defaults together with [Content and Visual Layout Standards](content-and-visual-layout.md). Instructions for the current task take precedence. Adapt the examples to the actual subject, exam, available tools, and source material.

## 1. Deliverable and reading experience

- Deliver a complete LaTeX project and a compiled PDF. The guide should work in print and on a tablet.
- Follow the syllabus or exam-outline order. Use a clear knowledge-card design, a restrained blue palette, and a consistent hierarchy.
- For each topic, present the framework, then its detailed explanation, followed by relevant past questions.
- Keep the publication focused on the learner. Place source inventories, exclusions, build notes, and production history in project documentation rather than in the book.

## 2. Scope and selection

1. Use the exam scope provided by the user and the current syllabus or outline. Exclude unrelated subjects and out-of-scope extensions.
2. Include every supplied past question that tests an in-scope concept, including recalled questions and question-bank items. A question with an out-of-scope scenario can still be in scope when its central skill is part of the exam.
3. Record excluded questions and the reason for each exclusion. Resolve only genuine scope ambiguity with the user, while continuing independent work.
4. Label each question with its year or source, such as `[2024 recalled]`, `[2012]`, or `[question bank]`.
5. Verify answers against supplied official keys or authoritative sources. Record uncertainty precisely; do not invent an answer.

## 3. Suggested project structure

```text
<subject>-exam-review/
├── main.tex                    Cover, contents, chapter imports, optional closing page
├── preamble.tex                Fonts, colors, page design, and reusable macros
├── body/
│   ├── ch1.tex                 Chapter explanations
│   └── chN.tex
├── gen/
│   ├── q_ch1.tex               Chapter questions and practice
│   └── q_chN.tex
├── img/                        Source figures and optional closing-page image
├── BUILD.md                    Build and usage instructions
└── <subject>-exam-review.pdf   Compiled deliverable
```

Keep explanations in `body/chN.tex` and questions in `gen/q_chN.tex`. Import each chapter's question file at the end of its body file. Set the number and names of chapters from the current syllabus.

## 4. Chapter and topic structure

- Follow the syllabus order and official chapter titles.
- Include lectures, practicals, and labs according to the stated exam scope.
- Within each chapter, place the overview first, detailed topic cards next, and relevant questions after the explanations.
- Before drafting, create a chapter map with chapter number, official title, exam scope, and matching sources. Proceed directly when the user's scope is explicit.

## 5. Knowledge-card pattern

Use only the components that make the information easier to learn. Tables work well for classifications, comparisons, stages, and differential features.

```latex
\chapter{<Official chapter title>}
\section{<Topic title>}
\begin{defbox}
\kw{<Key term>}: <A concise, accurate definition.>
\end{defbox}
\block{1. <Key concept>}
\begin{center}
\begin{tabularx}{\textwidth}{@{}lYl@{}}
\toprule
\textbf{<Feature>} & \textbf{<Description>} & \textbf{<Distinction>} \\
\midrule
\kw{<High-yield item>} & <Explanation> & <Key distinction> \\
\bottomrule
\end{tabularx}
\end{center}
\warn{<Common error or important condition.>}
\tip{<Concise supporting point.>}
\begin{memoryaid}
<A short, accurate mnemonic or recall cue.>
\end{memoryaid}
```

Suggested roles for reusable macros:

- `\block{...}` introduces a numbered blue key-point bar.
- `defbox` highlights a definition or central concept.
- `\tip{...}` presents a concise supporting point.
- `\warn{...}` highlights a common error or condition requiring attention.
- `memoryaid` presents a short recall aid in KaiTi where available.
- `\kw{...}`, `\accent{...}`, and `\secondary{...}` distinguish high-, medium-, and lower-priority terms with restrained color.
- `\singlechoice{...}`, `\multiplechoice{...}`, and `\answer{...}` format questions and answers.

Use `\textsuperscript{...}` and `\textsubscript{...}` for units and notation. Check all symbols in the rendered PDF.

## 6. Optional closing page

Add a closing page only when the user requests one or supplies an image for the current project. Place its file under `img/`, then import it after all chapters and before `\end{document}`. Give it its own page, omit running headers and footers, preserve its aspect ratio, and center it within the available page area.

```latex
\clearpage
\thispagestyle{empty}
\begin{center}
\vspace*{\fill}
\includegraphics[width=\textwidth,height=\textheight,keepaspectratio]{img/closing-page.png}
\vspace*{\fill}
\end{center}
```

For multiple closing images, place each on its own page in the order the user specified.

## 7. Reusable `preamble.tex`

Adapt this starting point to the installed TeX distribution and the user's font requirements. In this workflow, SimHei (黑体) is for headings, SimSun (宋体) for body text, and KaiTi (楷体) for tables, typeset figure labels and captions, and supplementary content. Original handwriting retains its source glyphs. If a font is unavailable, use a suitable installed substitute, record it in `BUILD.md`, and inspect the rendered pages.

The Unicode fallbacks below prevent common symbols from disappearing during compilation. Confirm that the chosen fonts include the characters in use.

```latex
\documentclass[11pt,openany,oneside,fontset=windows]{ctexbook}
\xeCJKsetup{CheckSingle=true}
\setmainfont{SimSun}[BoldFont=SimHei,ItalicFont=KaiTi]
\setsansfont{SimHei}[BoldFont=SimHei]
\setCJKmainfont{SimSun}[BoldFont=SimHei,ItalicFont=KaiTi]
\setCJKsansfont{SimHei}[BoldFont=SimHei]
\setCJKfamilyfont{hei}[BoldFont=SimHei]{SimHei}
\setCJKfamilyfont{kai}[BoldFont=KaiTi]{KaiTi}
\newfontfamily\kaitifont{KaiTi}[BoldFont=KaiTi]
\newcommand{\kaicontent}{\kaitifont\kaishu}

\usepackage{geometry}
\geometry{a4paper,top=2.2cm,bottom=2.2cm,left=2cm,right=2cm,headheight=14pt}
\usepackage{xcolor,amsmath,amssymb}
\usepackage{booktabs,array,longtable,multirow,tabularx,enumitem}
\usepackage{etoolbox}
\AtBeginEnvironment{tabular}{\kaicontent}
\AtBeginEnvironment{tabularx}{\kaicontent}
\AtBeginEnvironment{longtable}{\kaicontent}
\AtBeginEnvironment{figure}{\kaicontent}
\AtBeginEnvironment{figure*}{\kaicontent}
\usepackage{caption}
\DeclareCaptionFont{kaicap}{\kaicontent}
\captionsetup{font=kaicap}
\newenvironment{supplement}{\begingroup\kaicontent}{\endgroup}

\usepackage{tcolorbox}
\tcbuselibrary{skins,breakable}
\usepackage{titlesec,titletoc,fancyhdr,graphicx}
\usepackage[hidelinks]{hyperref}
\definecolor{navy}{RGB}{31,56,120}
\definecolor{titleblue}{RGB}{37,64,143}
\definecolor{lightblue}{RGB}{222,232,247}
\definecolor{boxblue}{RGB}{47,84,150}
\definecolor{keywordred}{RGB}{192,0,0}
\definecolor{orange}{RGB}{197,90,17}
\definecolor{green}{RGB}{0,110,80}
\definecolor{rulegray}{RGB}{60,60,90}
\definecolor{boxbg}{RGB}{248,250,253}
\linespread{1.22}
\setlength{\parindent}{0pt}
\setlength{\parskip}{3pt}

\pagestyle{fancy}
\fancyhf{}
\renewcommand{\headrulewidth}{0.4pt}
\fancyhead[L]{\small\color{rulegray}<Subject> Exam Review}
\fancyhead[R]{\small\color{rulegray}\leftmark}
\fancyfoot[C]{\small\color{rulegray}\thepage}
\renewcommand{\chaptermark}[1]{\markboth{#1}{}}
\titleformat{\chapter}[hang]{\normalfont\sffamily\heiti\huge\bfseries\color{titleblue}}{\thechapter.}{0.4em}{}[\vspace{2pt}{\color{titleblue}\rule{\textwidth}{1.2pt}}]
\titleformat{\section}{\normalfont\sffamily\heiti\Large\bfseries\color{titleblue}}{\thesection}{0.6em}{}[\vspace{1pt}{\color{titleblue}\rule{\textwidth}{0.6pt}}]
\titleformat{\subsection}{\normalfont\sffamily\heiti\large\bfseries\color{navy}}{\thesubsection}{0.5em}{}
\titlespacing*{\chapter}{0pt}{2pt}{12pt}
\titlespacing*{\section}{0pt}{10pt}{6pt}
\titlespacing*{\subsection}{0pt}{8pt}{4pt}

\newcommand{\block}[1]{\vspace{4pt}\noindent\begin{tcolorbox}[enhanced,colback=lightblue,colframe=lightblue,boxrule=0pt,arc=1pt,left=8pt,right=6pt,top=3pt,bottom=3pt,boxsep=1pt]{\sffamily\heiti\bfseries\color{navy}#1}\end{tcolorbox}\vspace{2pt}}
\newtcolorbox{defbox}{enhanced,breakable,colback=boxbg,colframe=boxblue,boxrule=0.8pt,arc=2pt,left=8pt,right=8pt,top=5pt,bottom=5pt}
\newtcolorbox{memoryaid}{enhanced,breakable,colback=white,colframe=navy,boxrule=0.6pt,arc=1pt,left=8pt,right=8pt,top=4pt,bottom=4pt,fontupper=\kaishu\color{navy}}
\newcommand{\tip}[1]{\vspace{2pt}\noindent{\color{boxblue}$\blacktriangleright$\ }{\color{boxblue}#1}\par}
\newcommand{\warn}[1]{\vspace{2pt}\noindent{\color{keywordred}!\ }#1\par}
\newcommand{\kw}[1]{{\color{keywordred}\bfseries #1}}
\newcommand{\accent}[1]{{\color{orange}\bfseries #1}}
\newcommand{\secondary}[1]{{\color{green}\bfseries #1}}
\newcommand{\singlechoice}[1]{\vspace{3pt}\noindent{\bfseries\color{boxblue}[Single choice]} #1\par}
\newcommand{\multiplechoice}[1]{\vspace{3pt}\noindent{\bfseries\color{boxblue}[Multiple choice]} #1\par}
\newcommand{\answer}[1]{\noindent{\bfseries\color{keywordred}Answer: }#1\par}
\setlist[itemize]{leftmargin=1.4em,topsep=2pt,itemsep=1pt,parsep=0pt}
\setlist[enumerate]{leftmargin=1.6em,topsep=2pt,itemsep=1pt,parsep=0pt}
\newcolumntype{Y}{>{\raggedright\arraybackslash}X}
\renewcommand{\arraystretch}{1.15}
\renewcommand\tabularxcolumn[1]{m{#1}}

\usepackage{newunicodechar}
\newfontfamily\symfont{SimSun}
\newunicodechar{≤}{{\symfont\char"2264}}
\newunicodechar{≥}{{\symfont\char"2265}}
\newunicodechar{β}{{\symfont\char"03B2}}
\newunicodechar{∶}{:}
\newunicodechar{Ⅰ}{{\symfont\char"2160}}
\newunicodechar{Ⅱ}{{\symfont\char"2161}}
\newunicodechar{Ⅲ}{{\symfont\char"2162}}
\newunicodechar{Ⅳ}{{\symfont\char"2163}}
\newunicodechar{Ⅴ}{{\symfont\char"2164}}
\newunicodechar{Ⅵ}{{\symfont\char"2165}}
\newunicodechar{Ⅶ}{{\symfont\char"2166}}
\newunicodechar{Ⅷ}{{\symfont\char"2167}}
\newunicodechar{Ⅸ}{{\symfont\char"2168}}
\newunicodechar{Ⅹ}{{\symfont\char"2169}}
\newunicodechar{①}{{\symfont\char"2460}}
\newunicodechar{②}{{\symfont\char"2461}}
\newunicodechar{③}{{\symfont\char"2462}}
\newunicodechar{④}{{\symfont\char"2463}}
\newunicodechar{⑤}{{\symfont\char"2464}}
\newunicodechar{⑥}{{\symfont\char"2465}}
\newunicodechar{⑦}{{\symfont\char"2466}}
\newunicodechar{⑧}{{\symfont\char"2467}}
\newunicodechar{⑨}{{\symfont\char"2468}}
\newunicodechar{⑩}{{\symfont\char"2469}}
```

The example assumes a suitable CJK TeX installation on Windows. Verify the class, font names, and Unicode glyph coverage against the actual environment. Use a different compatible setup when required, then inspect the rendered result.

## 8. Chapter questions and practice

Use the question types present in the actual exam. Place original questions before any newly written practice questions. Match difficulty and style to the subject's relevant authoritative examinations when that is useful.

```latex
\block{Past questions: <Exam question types> (<Topic>)}
\ptag{Short answer}
{\bfseries <Original question stem>} {\small\color{rulegray}[2024 recalled]}\par
Key points: (1) ...; (2) ...; (3) ...\par

\block{Practice: <Topic>}
\singlechoice{\textnormal{[Question bank]} <Question stem>?\\
A. ... \quad B. ... \quad C. ... \quad D. ...}
\answer{C. <Brief rationale.>}
```

Define a question block by the real exam type, not by a generic template. Keep the original stem and its source label intact. Clearly label newly authored questions as practice.

## 9. Question inventory and build checks

### Question inventory

1. Inventory all supplied lectures, notes, past papers, recalled papers, question banks, answer keys, photos, and screenshots.
2. Extract text from documents and PDFs with appropriate tools. Inspect each image directly and transcribe its question stem; filenames are not evidence of image contents.
3. Record each question's source/year, actual exam type, topic, scope decision, and handling status.
4. Keep in-scope items, assign them to chapters, and record the reason for each exclusion.
5. Compare the inventory against existing question blocks and add only missing questions.
6. Verify answers against available official keys before publication.
7. Reconcile the delivered question sets with the roster. Keep source files synchronized if the project uses separate build and delivery copies.

### Compilation and review

- Compile with XeLaTeX or LuaLaTeX three times so contents entries and page references settle.
- Record font substitutions in `BUILD.md`. Recompile and inspect page breaks after a font change.
- Before delivery, check balanced braces and environments, successful compilation, missing-character warnings, special glyphs, contents and page numbers, chapter order, figure references, and any requested closing page.
- Render and review the final PDF. Verify the actual page layout rather than treating successful text extraction or a successful compile as sufficient.
- Deliver the source project, compiled PDF, build instructions, and the image asset if the project uses one.

## 10. Reusable prompt template

Copy this prompt, replace bracketed fields, and provide the relevant current source materials:

```text
Create or revise an exam review guide for [subject], following the supplied syllabus and the scope below.

Deliver a complete LaTeX source project, a compiled PDF, and concise build instructions. Use a single-column layout. Apply SimHei to headings, SimSun to body text, and KaiTi to tables, typeset figure labels and captions, and supplementary content. Preserve source lettering in original handwritten notes and designated screenshots.

1. Scope: Cover [exam scope]. Record out-of-scope items and reasons in the project audit notes. Ask only when a material ambiguity remains.
2. Chapter order: Follow the official titles and sequence in [syllabus or exam outline].
3. Topic structure: For each topic, place its original framework image before the matching detailed explanation, then add relevant past questions.
4. Editorial style: Keep core coverage complete and remove repeated material. Write new explanations and advice in formal, concise language. Preserve verbatim passages and original question wording when requested.
5. Questions: Include all supplied in-scope past questions across the agreed deliverables. Inspect photographs and screenshots directly, mark each source and year, deduplicate exact repeats, and verify answers against supplied keys or authoritative references. Label newly written questions as practice.
6. Figures and tables: Match each image to its topic and body text. Crop at complete semantic boundaries. Use clear source tables when readable; otherwise typeset them with intact rows and readable labels. Avoid repeated headings on continuation fragments.
7. Build and review: Compile the complete project three times with XeLaTeX or LuaLaTeX when available. Check glyphs, page breaks, contents, numbering, and all final rendered pages. Report any unresolved source or verification issue.
8. Closing page: Add one only if requested or supplied for this project; preserve its aspect ratio and place it after all chapters.

At delivery, provide the PDF and complete source project. Summarize out-of-scope exclusions, unresolved questions, font substitutions, and any verification that could not be completed.
```

### Final checklist

Scope matches the user's instructions; chapters follow the syllabus; actual exam types guide the question sections; frameworks align with explanations; all in-scope questions are accounted for; answers have evidence; images and tables are legible and complete; the layout is single-column; specified fonts are applied or substitutions are recorded; symbols render; the contents and page references are correct; the final PDF has been visually reviewed; source and PDF deliverables are synchronized.
