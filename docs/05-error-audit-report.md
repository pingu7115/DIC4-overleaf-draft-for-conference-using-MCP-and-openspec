# DIC4 Error Audit & Fix Report (`paper_bad/` → `paper/`)

本報告記錄 Agent 針對初版草稿（[paper_bad/main.tex](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper_bad/main.tex)）進行自動化檢查後所發現的錯誤，以及在修正版（[paper/main.tex](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper/main.tex)）中的修復方式。

## 錯誤清單與修正對照表

| 編號 | 錯誤類別 | 壞版本 (`paper_bad/main.tex`) 問題 | 修正版 (`paper/`) 修復方式 |
|:---:|:---|:---|:---|
| **E1** | **Abstract A–F 缺漏** | 缺少 **Checkpoint B (But/Challenge)** 與 **Checkpoint E (Experiments)**，且缺少 `\begin{IEEEkeywords}` | 在 [00_abstract.tex](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper/sections/00_abstract.tex) 完整補齊 A–F 六大 Checkpoint 註解與對應內容，並補上 `IEEEkeywords` |
| **E2** | **學術誠實度違規（虛構數據）** | 違反 `openspec/config.yaml` 規範，在 Proposal 階段虛構 `96.8% Macro-F1` 與 `0.4% miss rate` | 移除所有虛構數據，於 Abstract Checkpoint F 與 [04_experiment.tex](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper/sections/04_experiment.tex) 改為嚴謹的 **Evaluation Plan & Expected Outcomes** |
| **E3** | **LaTeX 語法與引用錯誤** | 1. 內文 `5%` 未跳脫導致該行後半段被註解<br>2. 引用不存在的 `\cite{unknown_ref_2026}` 與 `\ref{fig:missing_arch}` 產生 `[?]` 與 `??` | 1. 全面跳脫 `\%` 與 `\&`<br>2. 建立完整 26 筆 [references.bib](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper/references.bib) 並驗證所有 `\cite{}` 與 `\ref{}`（含 `fig:arch`、`tab:related_work`、`tab:eval_plan`、`alg:triage`、`alg:fusion`）皆可解析 |
| **E4** | **IEEE 期刊格式不符** | 使用 `\documentclass[12pt,onecolumn]{article}` 且表格 `\caption` 放在表格下方 | 改用 `\documentclass[conference]{IEEEtran}` 雙欄會議格式，將所有表格 `\caption` 移至表格上方並使用 `booktabs` |
| **E5** | **演算法與 OpenSpec 規格不一致** | 融合邏輯僅取 `argmax(s)`，遺漏 NFR2 / M3 要求的 $\tau_{\text{safety}}$ 安全重標註與 `IsSufficient(E)` 檢查 | 在 [03_proposed_design.tex](file:///c:/Users/88693/Desktop/DIC4%20overleaf draft%20for%20conference%20using%20MCP%20and%20openspec/paper/sections/03_proposed_design.tex) 完整實作 Algorithm 1（24 行）與 Algorithm 2（包含 `high_risk` 與 $p_{\text{TP}} \ge \tau_{\text{safety}}$ 重標註） |

## 兩份 PDF 交付說明
- **壞 PDF（`paper_bad.pdf`）**：由 `paper_bad/main.tex` 編譯，呈現單欄非 IEEE 格式、文字截斷、`[?]`/`??` 斷鏈與虛構數據錯誤。
- **好 PDF（`paper_good.pdf`）**：由 `paper/main.tex` 編譯，呈現完整 IEEEtran 雙欄會議格式、TikZ 八大模組架構圖、Algorithm 1/2 虛擬碼、26 篇 IEEE 文獻引用與完整 A–F / A2Z 結構。
