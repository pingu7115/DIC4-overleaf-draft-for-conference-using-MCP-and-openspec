# IEEE Conference Paper Draft (`paper/`)

This directory contains the corrected, OpenSpec-verified IEEE Conference LaTeX draft for **AI SOC Analyst Agent** (`DIC4`).

## Structure
- `main.tex`: Root IEEEtran conference document
- `preamble.tex`: LaTeX packages (`IEEEtran`, `amsmath`, `algorithm`, `booktabs`, `tikz`, `cite`)
- `authors.tex`: Group 16 author block
- `references.bib`: 26 IEEE-formatted bibliography entries
- `sections/00_abstract.tex`: Abstract with Checkpoints A–F and `IEEEkeywords`
- `sections/01_introduction.tex`: Introduction (A2Z G–L, 5 Cores, 3 Trade-offs)
- `sections/02_related_work.tex`: Related Work (A2Z M–O, Article Summary Table, Research Gap)
- `sections/03_proposed_design.tex`: Proposed System Architecture (A2Z PA–PM, TikZ diagram, Algorithms 1 & 2)
- `sections/04_experiment.tex`: Evaluation Plan (A2Z Q–V, GUIDE & ExCyTIn-Bench, Expected Outcomes)
- `sections/05_conclusion.tex`: Conclusion & Future Work (A2Z W–Z)

## Compiling on Overleaf
Upload or sync `paper/` to Overleaf with `main.tex` as the root document and `pdfLaTeX` as the compiler.
