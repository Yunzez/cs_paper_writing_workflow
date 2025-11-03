## General Style

*   **Narrative Flow:** Prefer a natural, narrative writing style over bulleted or enumerated lists (`itemize`, `enumerate`). Use prose to connect ideas and create a smooth flow of information. bullet points can be used sparingly for emphasis or clarity, but the main content should be in paragraph form.
*   **Structured Documents:** Use clear and hierarchical document structures. Employ `subsection`s to break down complex topics into logical, manageable parts.
*   **Elaborate on Concepts:** When introducing technical concepts, provide detailed explanations. Don't assume the reader is already an expert. For example, when mentioning "DWARF scope chain resolution," explain what it is and how it works.
*   **Integrate Figures:** When figures are available, they should be included in the document. The surrounding text must be adapted to refer to and describe the figures, explaining their relevance and what they illustrate.
*   **Use Concrete Examples:** To clarify complex topics, use concrete examples. This can include code snippets, data excerpts (like DWARF output), or step-by-step walkthroughs of a process.
*   **Structure:** Recursively apply intro - body - conclusion paragraph structure within sections and subsections to enhance clarity and flow. Tell why the section matters first. Don't use subsubsections, use paragraphs when necessary.
*  **Reduce use of ; and -–:** Prefer sentences with better readability.

## LaTeX Specific

*   **Underscores:** To ensure proper compilation and robustly handle literal strings, use the `\detokenize{}` command for words that contain underscores. This is the preferred method. For example, `DW_AT_location` should be written as `\texttt{\detokenize{DW_AT_location}}`.
*   **Text Formatting:** Use `\texttt{}` for code-like text (e.g., variable names, function names) and `\textit{}` for emphasis or to introduce key terms. Never use ` or _ or * for formatting. Use - instead of \- for hyphenation in text.
*   **Citation Placeholders:** Use [CITATION] as a placeholder for citations. or use a descriptive placeholder like [DWARF SPEC] if the citation is to a specific document.