---
lab_step: true
---

# 啟用 ERP MCP

在 FO 檢查動態 MCP 功能和 Copilot Studio 用戶端。若你沒有管理權限，請 FO 管理員在同一個測試環境操作。

## 檢查 MCP 功能

1. 在 FO 開啟 **功能管理（Feature management）** 工作區。
2. 搜尋 **Dynamics 365 ERP Model Context Protocol server**。
3. 確認功能已啟用。若環境顯示功能可啟用，請管理員啟用。若找不到功能，先核對第一關的環境類型與版本。[MCP 功能需求](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp#prerequisites)

## 確認允許 Copilot Studio

1. 開啟 **系統管理 → 設定 → Allowed MCP clients（System administration → Setup → Allowed MCP clients）**。
2. 找到 **Microsoft Copilot Studio**，確認 **Allowed** 已開啟。若清單與預設不同，請管理員對照 Microsoft 公布的用戶端 ID 後設定。[Allowed MCP clients 與用戶端 ID](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/mcp/mcp-security#allowed-mcp-clients)
3. 保留這個 FO 測試環境的網址，下一關建立連線時用來核對目標。

!!! success "過關條件"
    FO 已啟用動態 ERP MCP，Copilot Studio 在允許清單內，而且你已確認要連線的 FO 環境。
