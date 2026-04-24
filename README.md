# my-claude-brain

Claude 對我的長期記憶——跨對話、跨電腦保留的個人檔案。

這個 repo 就是 Claude Code 在每次對話開始時會讀取的那個 `memory/` 資料夾，版本化起來是為了：
- **觀察記憶如何演進**——隨著時間看到 Claude 對我的理解怎麼長出來
- **跨電腦同步**——換新機器時不會失去累積的脈絡
- **備份**——意外刪除也能救回

## 結構

```
MEMORY.md               索引，每次對話開始會載入（<200 行）
user_*.md               關於我是誰、角色、偏好、知識
feedback_*.md           我給過 Claude 的指正 / 認可
project_*.md            正在進行的工作、目標、事件
reference_*.md          外部系統指路（Linear / Notion / Slack 等）
```

每個 memory 檔案有 YAML frontmatter（`name` / `description` / `type`），內容是 markdown。

## 實際位置

這個資料夾實際存在：
```
~/.claude/projects/-Users-archer-Documents-ai-claude-room/memory/
```

那串 `-Users-archer-Documents-ai-claude-room` 是由工作目錄 `/Users/archer/Documents/ai/claude-room` 編碼而來（`/` → `-`）。**換電腦時路徑中的使用者名稱若不同，資料夾名也要對應修改**，否則 Claude Code 不會讀到。

## 工作流程

Claude 在對話中自行讀寫這個資料夾。我偶爾會：
- `git log` 看看最近記憶怎麼改的
- `git diff` 看單次對話學到了什麼
- 手動編輯修正錯誤記憶
