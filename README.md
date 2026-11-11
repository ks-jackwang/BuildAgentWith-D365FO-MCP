# Dynamics 365 FO 實作 Lab

用 Copilot Studio 和動態 Dynamics 365 ERP MCP 建立一個唯讀客戶查詢代理。學員從 FO 測試環境選定客戶，在活動圖確認工具呼叫，回到 FO 核對客戶群組和幣別。

在 [GitHub Pages 開始實作](https://ks-jackwang.github.io/BuildAgentWith-D365FO-MCP/)，或直接閱讀[工作坊總覽原始檔](docs/index.md)。適用環境包括符合版本需求的 FO UDE 與 Tier 2 以上沙箱。

## 在本機預覽

在專案根目錄用 Python 3.10 以上版本執行以下指令。GitHub Actions 使用 Python 3.12。

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
mkdocs serve
```

在瀏覽器開啟 [本機預覽](http://127.0.0.1:8000/)。用 `mkdocs build --strict` 產生 `site/` 並檢查站內連結。

## 專案結構

| 路徑 | 用途 |
| --- | --- |
| `docs/index.md` | 工作坊首頁和關卡入口 |
| `docs/lab/` | 五關教材與驗收步驟 |
| `docs/troubleshooting.md` | 環境、連線和查詢排查 |
| `docs/sources.md` | 教材來源與授權 |
| `docs/stylesheets/lab.css`、`overrides/main.html` | 首頁樣式與進度列 |
| `mkdocs.yml`、`requirements.txt` | 網站導覽與建置依賴 |
| `.github/workflows/pages.yml` | 建置與部署 GitHub Pages |

## 發布到 GitHub Pages

1. 將專案檔案放在目標 repository 的根目錄。若 repository 已有 Pages 網站，先確認這個 Lab 的發布路徑與既有部署設定。
2. 由 repository 管理員或維護者開啟 **Settings → Pages**，在 **Build and deployment → Source** 選 **GitHub Actions**。[設定 Pages 發布來源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
3. 推送到預設分支，或在 **Actions** 開啟 **Build and publish the Lab**，從預設分支執行 **Run workflow**。
4. 等待部署成功，再開啟部署工作所列的 Pages URL，確認首頁和第一關可以載入。

工作流程會從 GitHub Pages 讀取站點 URL，因此同一份設定可用在不同的 repository 路徑。Pull request 會建置網站，部署則由預設分支觸發。

## 來源與授權

詳見[來源與授權](docs/sources.md)。
