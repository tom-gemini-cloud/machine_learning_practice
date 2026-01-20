---
name: update-notes-from-notebook
description: Extract markdown from Jupyter notebooks and sync to markdown notes files with UK spellings. Use when the user asks to update notes, sync notebook to notes, build up notes, export notebook content, or convert notebook to markdown.
---

# Update Notes from Notebook

Extract markdown content from Jupyter notebooks and synchronize to markdown notes files using British English spellings.

## When to Use

Apply this skill when the user wants to:
- Update markdown notes from a notebook
- Sync notebook content to notes files
- Extract documentation from notebooks
- Build up cumulative notes from practice notebooks

## Process

1. **Identify files**:
   - Notebook: Use the provided `.ipynb` file path (from user or `$ARGUMENTS`)
   - Notes file: Infer the corresponding `_notes.md` file in the same directory (e.g., `classification_practice.ipynb` → `classification_notes.md`)
   - If the naming pattern is unclear, ask the user which notes file to update

2. **Extract and convert**:
   - Read the notebook and extract all markdown cells (skip code cells)
   - Convert American to British spellings (modelling, maximise, analyse, etc.)
   - Preserve all LaTeX math notation and markdown formatting exactly

3. **Update notes file**:
   - Write the converted content to the notes file
   - Confirm which file was updated

## Edge Cases

- **No obvious notes file**: Ask the user where to save the notes
- **Alternative naming**: Adapt to project-specific naming conventions
- **Empty notebook**: Inform the user if there's no markdown content to extract

## Important

- Preserve LaTeX math exactly (e.g., `$\mathbf{x}$`, `$$...$$`)
- Keep all markdown structure intact (headers, lists, bold, italic)
- Only modify spelling, never mathematical notation or code
