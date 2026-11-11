---
lab_step: true
---

# 建立並連接代理

建立一個練習用代理，讓它透過動態 MCP 查詢 FO。

## 建立代理

1. 開啟 [Copilot Studio](https://copilotstudio.microsoft.com/)，核對目前的 Power Platform 環境。
2. 建立採用標準編排（standard harness）的代理，命名為 `FO 客戶查詢 Lab`。在代理設定中確認已啟用 **生成式編排（Generative orchestration）**。[Copilot Studio 生成式編排](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-generative-actions)
3. 在 **概觀（Overview）** 檢查模型。若測試時代理經常選錯工具，依租戶允許的模型與 Microsoft 的當前建議調整。[ERP MCP 的模型選擇](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/build-agent-mcp#selecting-a-model)

## 加入動態 MCP 連線

1. 在代理的 **工具（Tools）** 頁面選 **新增工具（Add a tool）**，以 **Model Context Protocol** 篩選。
2. 搜尋 **Dynamics 365 ERP MCP**，開啟對應的伺服器。若搜尋結果有相近的名稱，在加入後以工具清單辨認動態版。
3. 建立或選擇連線。使用第一關的測試身分登入，依連線畫面提供的選項指定 FO 測試環境。核對登入帳號和環境後，選 **Add to agent** 或 **Add and configure**。[在 Copilot Studio 加入 MCP 伺服器](https://learn.microsoft.com/en-us/microsoft-copilot-studio/mcp-add-components-to-agent)
4. 從代理的 **工具** 清單開啟已加入的 MCP 伺服器，查看工具清單。尋找 `data_find_entity_type`、`data_get_entity_metadata` 和資料查詢工具 `data_find_entities` 或 `data_find_entities_sql`。Microsoft 文件指出，自 FO 10.0.48 起，後者取代前者。[動態資料工具清單](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp#data-tools)

!!! success "過關條件"
    代理的工具清單有 **Dynamics 365 ERP MCP**，而且你看得到動態資料查詢工具。第五關會確認連線能實際取得資料。
