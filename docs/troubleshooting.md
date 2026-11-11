# 常見問題

## FO 找不到 MCP 功能

先核對環境類型與應用程式版本。CHE 不支援動態 ERP MCP。若環境是 UDE，請在 Power Platform 管理中心確認它已部署 FO 應用程式，再請管理員檢查品質更新與功能管理。[支援的 FO 環境與版本](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp#prerequisites)

## Copilot Studio 找不到連接器

確認目前的 Power Platform 環境，從 **工具 → 新增工具 → Model Context Protocol** 搜尋。若清單仍缺少 **Dynamics 365 ERP MCP**，請管理員查閱該環境的連接器可用性與資料原則。若能選到連接器但連線失敗，再檢查 FO 的 **Allowed MCP clients**。[新增 MCP 工具](https://learn.microsoft.com/en-us/microsoft-copilot-studio/mcp-add-components-to-agent) · [FO 用戶端允許清單](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/mcp/mcp-security#allowed-mcp-clients)

## 連線成功但查詢失敗

在活動圖找出第一個失敗的工具。若登入或授權失敗，核對連線身分、FO 目標環境與允許的用戶端。若工具找不到客戶實體，請管理員核對該身分的資料實體讀取權限和公司的存取範圍，再回到第三關檢查連到的是動態 MCP。[ERP MCP 存取控制](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/mcp/mcp-security#authorization-and-access-control)

## 活動圖沒有 MCP 查詢或欄位對不上

用新對話重測，提供完整公司代碼和客戶帳號。若代理沒呼叫 MCP，確認生成式編排已開啟、MCP 工具已加入且已儲存指示。若代理呼叫了工具，核對輸入的公司與帳號，再比對工具輸出、代理回覆和 FO 畫面。若工具輸出和 FO 一致，從[代理指示](lab/04-instructions.md)檢查輸出欄位的要求。[檢視代理活動](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-review-activity)
