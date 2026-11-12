# 驗證紀錄

日期：2026-11-12。測試對象為 Release 快照的本輪本機改版。

執行：

```sh
node --test tests/quality.test.cjs review/character-studio/tests/*.test.cjs
```

目前 34 項通過：22 項學習快取／歷史／幾何／步態／島頁編譯／平板切頁測試，加上 8 項既有角色工作室回歸測試與 4 項原始快照候選 patch 測試。角色工作室是之前的 v0.2 原型，本輪並未宣稱重新製作完整蒙皮角色。

4 項候選 patch 測試針對交付的 `review/snapshot-base-island.html` 原始快照；本輪整合後島頁另有編譯、游泳姿態與平板狀態測試，不把原始候選 patch 測試視為完整遊戲驗收。

已檢查：原版／改版單主岩石三角形數為 748／320；位置、法線、頂點色沒有 NaN。島頁 classic inline scripts 可編譯。幾何數量改善不是端到端效能量測。

仍待補：本輪小型 3D 比較場景、平台導引鍵盤操作的瀏覽器視覺驗收；完整島嶼遊戲 E2E、行動裝置、真實 Supabase 錯誤／RLS、Classroom 授權與 AI API。先前瀏覽器自動化曾因無法可靠辨識網址中止，不能把它描述成上述項目都已通過。
