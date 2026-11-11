---
lab_step: true
---

# 準備環境與測試資料

先登入 FO 和 Copilot Studio，再從 FO 記下一筆測試客戶的欄位值。最後一關會用這筆資料判斷代理有沒有查對。

## 確認環境支援動態 ERP MCP

| FO 環境 | 可用性 |
| --- | --- |
| Power Platform 的 Unified Developer Environment（UDE），已部署 FO 應用程式 | 支援。一般 Power Platform 開發者環境須先確認是否為 FO UDE。 |
| Tier 2 或以上的 FO 沙箱 | 支援。 |
| Cloud Hosted Environment（CHE），例如從 Lifecycle Services 佈建至自有 Azure 訂用帳戶的開發 VM | 動態 ERP MCP 不支援。請改用符合條件的 UDE 或沙箱。 |

在 FO 開啟右上角的 **說明（Help）** 選單，從 **關於（About）** 記下應用程式版本。Microsoft 列出的最低版本為 **10.0.47**，或 **10.0.46 PQU-2**、**10.0.45 PQU-7**。請一併確認品質更新版本，並以最新文件為準。[動態 ERP MCP 的環境與版本需求](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp#prerequisites)

## 確認帳號和權限

1. 登入 [Copilot Studio](https://copilotstudio.microsoft.com/)，切換到可建立代理和連線的 Power Platform 環境。
2. 請環境管理員確認租戶允許這個連線，並確認 FO 和 Copilot Studio 授權及計費設定。[ERP MCP 計費說明](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp#licensing)
3. 以將用於 MCP 連線的測試身分登入 FO。請管理員授予指定測試公司的客戶資料讀取權限，並確認該身分可讀取練習用資料實體。下一關的功能與用戶端設定可由管理員協助。[ERP MCP 的身分與存取控制](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/mcp/mcp-security)

## 記下核對用資料

1. 在 FO 的公司選擇器切到測試公司，記下公司代碼。
2. 開啟 **應收帳款 → 客戶 → 所有客戶（Accounts receivable → Customers → All customers）**，挑一筆既有的範例客戶。
3. 開啟客戶明細，記下客戶帳號、客戶群組和幣別。請挑選這些欄位都有值的範例。
4. 留在同一間公司，在清單用客戶帳號精確篩選，確認另一個測試帳號查無資料。記下該帳號供最後一關使用。

| 練習中使用的代稱 | 從測試環境取得的值 |
| --- | --- |
| `<公司代碼>` | 目前的公司代碼 |
| `<客戶帳號>` | 確認存在的範例客戶帳號 |
| `<不存在的帳號>` | 在同一公司確認查不到的帳號 |
| 核對用欄位 | 客戶群組、幣別 |

!!! success "過關條件"
    你能進入 Copilot Studio 與支援的 FO 測試環境，手上也有一筆可核對的客戶資料和一個查不到的帳號。
