# 曙光學習：2026-11-12 審查交付

這個 fork 的舊 main 僅保留上游歷史；**本輪改動在本分支的 ZIP 與 patch 中**，不是把舊 main 當正式網站最新版。

- `Dawn-Quality-Review-20261112.zip`：改動後的學習／島嶼程式、模型原始碼、預覽、測試與報告。解壓後按包內 README 操作。
- `dawn-quality-20261112.patch`：只含 5 個正式執行檔的修改／新增。已對原始快照通過 git apply --check。
- `SITE-REVIEW-2026-11-12.md`：問題、修正、後續優先項目與實測界線。
- `VALIDATION.md`：34 項通過的測試與尚待驗收項目。

## 使用方式

先下載朋友提供的 [snapshot-2026-11-11](https://github.com/nashsung2-coder/dawn-edu-v4-staging/releases/tag/snapshot-2026-11-11) 完整快照，在獨立副本將 ZIP 內檔案依相對路徑覆蓋進去（保留快照的原資產）。**ZIP 是改動與審查套件，不是網站所有未改動資產的整包。** patch 是另一種套用正式執行檔改動的方式，兩種方式擇一，不能重複套用。

在合併後的目錄執行：

    node tools/review-server.cjs
    node --test tests/quality.test.cjs review/character-studio/tests/*.test.cjs

開啟 http://127.0.0.1:4175/ 。不需 npm install。模型為 JavaScript + Three.js 原型，沒有 .blend 檔。

## 權限與部署

這是公開 fork，朋友可直接閱讀、下載、clone 與提出 PR，不需要分享密碼或 token。寫入、合併權限依 GitHub 儲存庫設定另行確認。本輪沒有更動上游 main、Cloudflare 或正式站部署；請由網站維護者審查與實測後整合。
