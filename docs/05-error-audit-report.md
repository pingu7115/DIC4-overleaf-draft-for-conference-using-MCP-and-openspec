# DIC4 Error Audit & Fix Report (`paper_bad/` → `paper/`)

本報告記錄 Agent 針對初版 IEEE 會議論文草稿（[paper_bad/paper_bad.pdf](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper_bad/paper_bad.pdf)）進行 Overleaf 編譯日誌（`output.log`）與版面視覺檢查後所發現的錯誤，以及在修正版（[paper/paper_good.pdf](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper/paper_good.pdf)）中的修復方式。

## 錯誤清單與修正對照表

| 編號 | 錯誤類別 | 壞版本 (`paper_bad/`) 問題 | 修正版 (`paper/`) 修復方式 |
|:---:|:---|:---|:---|
| **E1** | **Table II 嚴重超出右欄邊界** | [04_experiment.tex](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper_bad/sections/04_experiment.tex) 中 `tab:eval_plan` 使用固定 `lll` 欄位未自動換行，編譯出現 `Overfull \hbox (50.54973pt too wide)`，導致右欄文字（如 `Correctness, Evidence Completeness`）被頁面邊界裁切 | 引入 `tabularx` 與 `ragged2e` 套件，改用 `\begin{tabularx}{\columnwidth}{@{}l>{\RaggedRight\arraybackslash}X>{\RaggedRight\arraybackslash}X@{}}` 搭配 `\footnotesize`，完全貼合單欄寬度（`0pt` overflow） |
| **E2** | **內文程式碼識別字超出邊界** | [03_proposed_design.tex](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper_bad/sections/03_proposed_design.tex) 第 44 行 `\texttt{Planner.IsSufficient(E)}` 無法斷行，編譯出現 `Overfull \hbox (8.98465pt too wide)` 突出右欄邊界 | 加上 `\allowbreak`（`\texttt{Planner.\allowbreak IsSufficient(E)}`）使長識別字可於點號處安全斷行，消除 `Overfull \hbox` |
| **E3** | **TikZ 架構圖未鎖定欄寬** | `fig:arch` TikZ 流程圖未限制寬度於 `\columnwidth`，在雙欄版面有溢出風險 | 使用 `\resizebox{\columnwidth}{!}{...}` 包覆 `tikzpicture`，確保八大模組架構圖嚴格對齊單欄寬度 |

## 兩份 PDF 驗證結果
- **壞 PDF（[paper_bad.pdf](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper_bad/paper_bad.pdf)）**：IEEEtran 雙欄草稿，包含 Table II 右側超出邊界裁切（`50.55pt too wide`）與第 3 節段落溢出（`8.98pt too wide`）。
- **好 PDF（[paper_good.pdf](file:///c:/Users/88693/Desktop/DIC4%20overleaf%20draft%20for%20conference%20using%20MCP%20and%20openspec/paper/paper_good.pdf)）**：經 Overleaf 雲端重新編譯並檢查 `output.log`，達成 **0 Errors、0 Warnings、0 Overfull hbox**，所有表格、圖表、演算法與邊界皆完全對齊。
