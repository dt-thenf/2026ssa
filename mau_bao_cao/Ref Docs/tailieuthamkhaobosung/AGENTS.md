# Project instructions

## Goal
Create a full LaTeX progress report for:
"Nghiên cứu, thiết kế hệ thống RFAR ứng dụng TinyML trên thiết bị biên phục vụ công tác phân tích hoạt động lính cứu hỏa theo thời gian thực trong tình huống khẩn cấp"

## Hard constraints
- MUST preserve the exact report form, style, layout, font, and structure of:
  - mau_bao_cao/scientific_research_cap_bo_2025_templates/main.tex
  - mau_bao_cao/scientific_research_cap_bo_2025_templates/main.pdf
- MUST use pdflatex-compatible LaTeX only
- MUST NOT change document class, margins, font setup, heading style, numbering style, page layout, or template structure unless strictly required by the template
- MUST prioritize content extraction from:
  1. mau_bao_cao/baocaotiendo.docx
  2. mau_bao_cao/scientific_research_cap_bo_2025_templates/main.tex
  3. mau_bao_cao/scientific_research_cap_bo_2025_templates/main.pdf
  4. mau_bao_cao/Accepted_26.07.2025/Sensors-91454-2025_Latex/jsen.tex
  5. mau_bao_cao/Accepted_26.07.2025/Sensors-91454-2025_Latex/jsen.pdf
  6. mau_bao_cao/Accepted_26.07.2025/Sensors-91454-2025_Manuscript.pdf
  7. mau_bao_cao/RFAR_A_Real-Time_Firefighter_Activity_Recognition_System_Using_Wearable_Accelerometer.pdf
  8. all files under mau_bao_cao/Ref Docs
- MUST reuse available chapter files, figures, tables, equations, and bib entries when relevant
- MUST keep citations academically appropriate and consistent
- MUST compile successfully with pdflatex
- MUST provide progress incrementally, not one-shot

## Execution behavior
- Do NOT stop to ask for confirmation between phases.
- Do NOT ask the user to review the plan before continuing.
- Proceed automatically through all workflow steps unless a blocking error occurs.
- If a source is missing or unreadable, record it in the missing-data list and continue with remaining sources.
- Do NOT overwrite the original template files unless explicitly requested.
- Create a separate working report file and preserve the template as reference.

## Source handling rules
- First inventory all files and subfolders in the workspace.
- If ZIP/RAR archives exist, unpack them first and inventory the extracted contents.
- Prefer reusing original figure files from source folders rather than screenshots from PDFs.
- Only extract figures/tables from PDFs when no original source files are available.
- Reuse LaTeX equations/tables/figure environments from source .tex files when suitable.
- Adapt captions, labels, and surrounding explanation so they fit a Vietnamese progress report context.
- Do not fabricate citations or bibliography entries.
- If a reference is incomplete, mark it clearly for completion rather than inventing details.

## Workflow
1. Inventory all files and identify reusable assets:
   - template
   - chapter skeletons
   - figure folders
   - .bib files
   - equations
   - tables
2. Read baocaotiendo.docx and derive required report sections.
3. Map required sections to the template structure.
4. Create:
   - source inventory
   - proposed chapter mapping
   - missing-data list
5. Draft the report chapter-by-chapter in Vietnamese academic style.
6. Reuse tables/equations/figure environments from source LaTeX when relevant.
7. Build references.bib from existing bib files and cited documents.
8. Compile using:
   - pdflatex
   - bibtex
   - pdflatex
   - pdflatex
9. Fix compile errors, missing figures, citation issues, and major formatting issues.
10. Produce final .tex and .pdf.

## Output rules
- Before writing full content, first produce:
  a) source inventory
  b) proposed chapter mapping
  c) missing-data list
- Then continue chapter by chapter automatically.
- Final deliverables must include:
  - main report .tex
  - references.bib
  - compiled .pdf
  - short build log summary of errors fixed