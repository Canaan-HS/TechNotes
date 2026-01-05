# GitHub API 基礎指南

## 倉庫管理 (Repository)

| API 類型               | 功能                         | URL / 格式                                                                                                                        | 備註                                         |
| ---------------------- | ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **Repositories API**   | 取得使用者或組織的 repo 列表 | `GET https://api.github.com/users/{username}/repos`<br>`GET https://api.github.com/orgs/{org}/repos`                              | 可加 `?type=all&sort=updated` 過濾           |
| **Repository Details** | 取得單個 repo 詳細資訊       | `GET https://api.github.com/repos/{owner}/{repo}`                                                                                 | 包含 description、分支、創建時間、license 等 |
| **Contents API**       | 讀取、更新、創建或刪除檔案   | `GET https://api.github.com/repos/{owner}/{repo}/contents/{path}`                                                                 | 回傳檔案內容 base64，可寫入或刪除            |
| **Trees API**          | 列出整個檔案樹               | `GET https://api.github.com/repos/{owner}/{repo}/git/trees/{branch}?recursive=1`                                                  | `recursive=1` 遞迴列出所有子資料夾及檔案     |
| **Branches API**       | 列出分支或取得單個分支       | `GET https://api.github.com/repos/{owner}/{repo}/branches`<br>`GET https://api.github.com/repos/{owner}/{repo}/branches/{branch}` | 檢查分支名稱、最新 commit sha                |
| **Tags API**           | 列出標籤（版本號）           | `GET https://api.github.com/repos/{owner}/{repo}/tags`                                                                            | 適合版本管理或更新檢查                       |
| **Releases API**       | 取得發行版本 / release 資訊  | `GET https://api.github.com/repos/{owner}/{repo}/releases`                                                                        | 包含 tag_name、name、assets（可下載檔案）    |

## 版本控制 (Version Control)

| API 類型        | 功能                          | URL / 格式                                                                                                                   | 備註                                  |
| --------------- | ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| **Commits API** | 取得 commit 歷史或單個 commit | `GET https://api.github.com/repos/{owner}/{repo}/commits`<br>`GET https://api.github.com/repos/{owner}/{repo}/commits/{sha}` | 查 commit message、author、日期、diff |

## 協作管理 (Collaboration)

| API 類型              | 功能           | URL / 格式                                                                                                                                  | 備註                                  |
| --------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| **Issues API**        | 議題管理       | `GET https://api.github.com/repos/{owner}/{repo}/issues`<br>`POST https://api.github.com/repos/{owner}/{repo}/issues`                       | 列出議題、創建新議題、管理 issue 狀態 |
| **Pull Requests API** | PR 管理        | `GET https://api.github.com/repos/{owner}/{repo}/pulls`<br>`GET https://api.github.com/repos/{owner}/{repo}/pulls/{number}`                 | 列出 PR、取得 PR 詳情、合併狀態       |
| **Forks API**         | 分支管理       | `GET https://api.github.com/repos/{owner}/{repo}/forks`<br>`POST https://api.github.com/repos/{owner}/{repo}/forks`                         | 取得分支列表、創建新分支              |
| **Invite API**        | 協作者邀請管理 | `GET https://api.github.com/repos/{owner}/{repo}/invitations`<br>`PUT https://api.github.com/repos/{owner}/{repo}/collaborators/{username}` | 管理倉庫協作者邀請                    |

## 社群互動 (Social)

| API 類型           | 功能                      | URL / 格式                                                                                                                                                                          | 備註                                       |
| ------------------ | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| **Starring API**   | 星標管理（收藏/取消收藏） | `GET https://api.github.com/user/starred/{owner}/{repo}`<br>`PUT https://api.github.com/user/starred/{owner}/{repo}`<br>`DELETE https://api.github.com/user/starred/{owner}/{repo}` | 檢查星標狀態、添加星標、移除星標           |
| **Stargazers API** | 取得星標使用者列表        | `GET https://api.github.com/repos/{owner}/{repo}/stargazers`                                                                                                                        | 查看誰給了星標，可用於分析受歡迎程度       |
| **Users API**      | 取得使用者資料            | `GET https://api.github.com/users/{username}`                                                                                                                                       | 包含 login、id、public_repos、followers 等 |

## 分析統計 (Analytics)

| API 類型             | 功能                   | URL / 格式                                                                                                                                      | 備註                               |
| -------------------- | ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------- |
| **Contributors API** | 取得貢獻者列表         | `GET https://api.github.com/repos/{owner}/{repo}/contributors`                                                                                  | 分析專案貢獻者和活躍度             |
| **Languages API**    | 取得專案使用的程式語言 | `GET https://api.github.com/repos/{owner}/{repo}/languages`                                                                                     | 了解專案技術棧                     |
| **Traffic API**      | 取得流量統計           | `GET https://api.github.com/repos/{owner}/{repo}/traffic/views`<br>`GET https://api.github.com/repos/{owner}/{repo}/traffic/clones`             | 查看專案訪問量、克隆次數等統計資料 |
| **Statistics API**   | 取得倉庫統計資料       | `GET https://api.github.com/repos/{owner}/{repo}/stats/contributors`<br>`GET https://api.github.com/repos/{owner}/{repo}/stats/commit_activity` | 取得貢獻者統計、提交活動等詳細統計 |

## 自動化 (Automation)

| API 類型                  | 功能                   | URL / 格式                                                                                                                            | 備註                                   |
| ------------------------- | ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------- |
| **Actions API**           | CI/CD 工作流程管理     | `GET https://api.github.com/repos/{owner}/{repo}/actions/runs`<br>`GET https://api.github.com/repos/{owner}/{repo}/actions/workflows` | 管理 GitHub Actions 工作流程和執行記錄 |
| **Webhooks / Events API** | 取得事件或管理 webhook | `GET https://api.github.com/repos/{owner}/{repo}/events`<br>`POST https://api.github.com/repos/{owner}/{repo}/hooks`                  | 自動化通知或 CI/CD 集成                |
| **Projects API**          | 專案看板管理           | `GET https://api.github.com/repos/{owner}/{repo}/projects`<br>`GET https://api.github.com/orgs/{org}/projects`                        | 管理 GitHub Projects 看板和卡片        |

## 搜尋 (Search)

| API 類型       | 功能            | URL / 格式                                                             | 備註                             |
| -------------- | --------------- | ---------------------------------------------------------------------- | -------------------------------- |
| **Search API** | 搜尋檔案或 repo | `GET https://api.github.com/search/code?q={query}+repo:{owner}/{repo}` | 搜尋檔案名稱或內容，回傳匹配結果 |

---

## 📝 使用說明

### 基礎 URL
```
https://api.github.com
```

### 認證方式
```bash
# Header 認證
Authorization: token YOUR_TOKEN

# 或在 URL 中
?access_token=YOUR_TOKEN
```

### 常用參數
- `?per_page=100` - 每頁結果數
- `?page=1` - 頁碼
- `?sort=updated` - 排序方式
- `?direction=desc` - 排序方向

### 狀態碼
- `200` - 成功
- `401` - 未認證
- `403` - 權限不足
- `404` - 資源不存在
- `422` - 參數錯誤