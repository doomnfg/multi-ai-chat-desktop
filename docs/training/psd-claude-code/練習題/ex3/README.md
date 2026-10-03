# 練習 3：做一個「驗收報告」Skill

⏱ 25 分鐘

## 情境

每次設備驗收完，都要把測試記錄整理成固定格式的驗收報告。請把這項工作做成 Skill，之後一句話就能產出報告。

## 練習資料

| 檔案 | 內容 |
|---|---|
| `test_log.txt` | IBM Power 主機的驗收測試記錄（模擬資料） |
| `template.md` | 驗收報告範本 |

## 操作步驟

1. 在 PowerShell 切換到練習資料夾並啟動：

    ```powershell
    cd D:\AI-Work\練習\ex3
    claude
    ```

2. 請 Claude 起草 Skill：

    ```
    在 .claude/skills/acceptance-report/ 建立一個產生驗收報告的 Skill，
    報告格式依 template.md（把 template.md 複製到 Skill 資料夾裡）。
    要求：只能使用測試記錄中的數據，缺少的標示「待補」，
    並附上完成後的檢核清單。
    ```

3. 打開 `.claude/skills/acceptance-report/SKILL.md`，檢查並修改：
    - `description` 有沒有寫清楚「做什麼」＋「什麼時候用」？
    - 檢核清單是否包含：項目數一致、FAIL 項目列入待辦、序號逐字相同？
4. 輸入 `/reload-skills` 載入新的 Skill（或用 `/exit` 離開後重新輸入 `claude`）
5. 輸入 `/skills`，確認清單中有 `acceptance-report`
6. 輸入 `/clear`，然後說：

    ```
    幫我把 test_log.txt 做成驗收報告
    ```

7. 確認 Claude 有使用這個 Skill，並檢查報告

## 檢查重點

- [ ] 測試項目總數與 `test_log.txt` 一致
- [ ] FAIL 項目有列入「異常與待辦」
- [ ] 沒有數據的項目標示為「待補」，沒有被補上數字
- [ ] 結論符合範本的判定規則
- [ ] 設備序號與記錄檔逐字相同

## 進階挑戰（有時間再做）

- 不說「驗收報告」，改說「整理一下這份測試記錄」，Claude 還會使用這個 Skill 嗎？如果不會，該怎麼修改 description？
- 直接輸入 `/acceptance-report test_log.txt` 呼叫 Skill
