# 示範指南：利用 GitHub Copilot 進行儲存庫分析和記錄增強

本指南為工程師逐步示範如何使用 GitHub Copilot 分析儲存庫、增強記錄功能以及估算工作量（LOE）。本示範模擬一名新工程師加入專案並有效使用 GitHub Copilot 的過程。

---

## 先決條件
1. **設定 VS Code**：
   - 安裝 [Visual Studio Code](https://code.visualstudio.com/)。
   - 複製 [Microsoft VS Code 儲存庫](https://github.com/microsoft/vscode)。
   - 安裝 [GitHub Copilot](https://github.com/features/copilot) 擴充功能。

2. **必要擴充功能**：
   - GitHub Copilot
   - GitHub Copilot Chat

3. **熟悉命令**：
   - 基本瞭解如何在 Copilot Chat 中使用 `@workspace` 命令。
   - 能夠瀏覽儲存庫結構。

---

## 示範結構
本示範包含三個任務：

1. **儲存庫分析**
2. **增強記錄功能**
3. **估算工作量（LOE）**

---

## 任務 1：儲存庫分析
### 目標：
全面瞭解儲存庫結構，並找到記錄功能所涉及的關鍵檔案。

### 步驟：
1. 在 VS Code 中開啟儲存庫。
2. 存取進階設定：
   - 開啟**擴充功能**面板。
   - 按一下 Copilot 齒輪圖示並選擇**設定**。
   - 根據需要編輯 JSON 設定。
3. 使用 `@workspace` 命令探索儲存庫：
   - 命令 1：`@workspace 這是我第一次查看此儲存庫，有哪些地方需要特別留意？`
   - 命令 2：`@workspace 如果我想改進記錄功能，應該修改哪個檔案？`
4. 利用 Copilot Chat 識別程式庫和架構：
   - 命令：`@workspace src/vs/platform/log/common/log.ts 檔案使用了哪些記錄程式庫或架構？`
5. 查看記錄涵蓋範圍和風格：
   - 命令：`@workspace 能否介紹一下整個應用程式所採用的記錄涵蓋範圍和風格？`

---

## 任務 2：增強記錄功能
### 目標：
透過新增時間戳記和記錄層級來改進記錄機制，以便更好地追蹤問題。

### 步驟：
1. 在 VS Code 中開啟 `src/vs/platform/log/common/log.ts`。
2. 查看目前的記錄實作：
   - 詢問 Copilot：`你會如何改進目前開啟的檔案，使其包含時間戳記？`
3. 提出潛在的增強方案：
   - 命令：`@workspace 你會如何增強 log.ts 檔案，使其支援記錄層級和時間戳記？`
4. 說明 Copilot 如何利用 `log.ts` 中的參考提供感知內容的解決方案。

---

## 任務 3：估算工作量（LOE）
### 目標：
估算實作擬議記錄增強功能所需的開發時間、複雜度和風險。

### 步驟：
1. 瞭解增強功能的範圍：
   - 命令：`@workspace 要在 log.ts 中實作記錄層級和時間戳記，可能還需要進行哪些變更？`
2. 評估相依性：
   - 命令：`@workspace 你能識別 src/vs/platform/log/common/log.ts 的相依性嗎？`
3. 評估外部工具：
   - 命令：`此儲存庫中是否已整合外部記錄工具？新增工具是否需要額外設定？`
4. 估算開發時間：
   - 命令：`為記錄功能實作記錄層級和時間戳記可能需要多長時間？`
5. 指出技術風險和相依性：
   - 命令：`修改 log.ts 中的記錄功能有哪些風險？這是否會影響應用程式的其他部分？`
6. 總結發現：
   - 命令：`總結這些記錄增強功能所需的開發工作量，並重點說明風險和相依性。`

---

## 總結
按照本指南操作，你將能夠：
- 使用 GitHub Copilot 和 `@workspace` 命令分析儲存庫結構。
- 透過時間戳記和記錄層級等具體改進來增強記錄功能。
- 估算擬議變更的工作量（LOE），包括時間、風險和相依性。

本示範展示了 GitHub Copilot 在簡化工程工作流程和高效解決複雜任務方面的強大能力。如需進一步說明或有任何疑問，可以使用 Copilot Chat 深入瞭解儲存庫的具體細節。

---

### 資源
- [Microsoft VS Code 儲存庫](https://github.com/microsoft/vscode)
- [VS Code 文件](https://code.visualstudio.com/docs)
- [記錄最佳實務](https://www.loggly.com/ultimate-guide/node-logging-basics/)
