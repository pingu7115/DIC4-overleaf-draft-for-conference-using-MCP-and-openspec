# IEEE Conference Style Checklist (`IEEEtran`)

1. **Document Class**: `\documentclass[conference]{IEEEtran}` (2-column, 10pt).
2. **Title & Authors**: Concise title; `\author{\IEEEauthorblockN{...}\IEEEauthorblockA{...}}`.
3. **Abstract & Keywords**: Single-paragraph `\begin{abstract}...\end{abstract}` covering Checkpoints A–F, followed by `\begin{IEEEkeywords}...\end{IEEEkeywords}`.
4. **Citations**: IEEE numeric style `\cite{key}`, sorted and grouped; no uncited `\bibitem` or missing keys in `references.bib`.
5. **Section Numbering**: Roman numerals (`I. INTRODUCTION`, `II. RELATED WORK`, etc.) handled by `IEEEtran`.
6. **Figures & Tables**:
   - Figures use `\begin{figure}[t]...\end{figure}` with `\caption{...}` below.
   - Tables use `\begin{table}[t]...\end{table}` with `\caption{...}` above and `\centering`.
   - Every figure/table must be referenced in prose via `\ref{...}` (no orphan floats, no `??`).
7. **Algorithms & Math**:
   - `algorithm` / `algorithmic` packages properly formatted without line overflow in 2-column width.
   - Equations numbered cleanly; all symbols (`\tau`, `\tau_{\text{safety}}`, `w_{\text{ml}}`, `w_{\text{llm}}`) defined consistently.
8. **Academic Integrity**:
   - Proposal-stage project: zero fabricated experimental metrics; use "planned", "will evaluate", and "expected outcomes".
