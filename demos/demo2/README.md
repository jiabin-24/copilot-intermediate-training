# 示範指南：Copilot Chat 編碼實務

本指南詳細介紹如何使用 GitHub Copilot Chat 在 PowerBI JavaScript 儲存庫中實作並驗證一個實用函式，重點關注效率、可維護性和最佳實務。

---

## 先決條件

1. **設定儲存庫**：
   - 複製 [PowerBI JavaScript 儲存庫](https://github.com/microsoft/PowerBI-JavaScript)。
   - 安裝 [Visual Studio Code](https://code.visualstudio.com/)，並安裝 GitHub Copilot 和 Copilot Chat 擴充功能。

2. **開發環境**：
   - 確保已安裝 Node.js 和 npm。
   - 確認已設定 Jest 以進行測試。

---

## 任務 1：實作 `calculatePercentage` 實用函式

### 目標
建立一個可重複使用的百分比計算實用函式，並處理除數為零等邊界情況。

### 步驟

1. **確定實用工具檔案**：
   - 使用 `@workspace` 找到放置實用函式的正確檔案：
     ```
     @workspace，我應該將新的百分比計算實用函式放在哪裡？
     ```

2. **建立函式**：
   - 要求 Copilot Chat 產生函式：
     ```
     你能用 JavaScript 編寫一個名為 calculatePercentage 的實用函式嗎？該函式接收 part 和 total 兩個參數並計算百分比。當 total 為零時，函式應傳回 0。
     ```

3. **處理邊界情況**：
   - 向 Copilot Chat 詢問其他邊界情況：
     ```
     我還應該為這個實用函式新增哪些測試案例？
     ```

4. **為函式撰寫文件**：
   - 新增函式及其參數的說明：
     ```
     重構以下檔案，新增一段簡短說明，描述該函式的用途和參數。
     ```

---

## 任務 2：產生單元測試

### 目標
使用 Jest 編寫並執行單元測試，以驗證 `calculatePercentage` 的功能。

### 步驟

1. **設定測試環境**：
   - 執行：
     ```
     npm test
     ```
   - 如果尚未安裝 Jest，請執行：
     ```
     npm install jest
     ```

2. **建立測試檔案**：
   - 使用 `@workspace` 找到測試目錄：
     ```
     @workspace，目前的測試目錄在哪裡？
     ```
   - 在該目錄中建立 `calculatePercentage.test.js`。

3. **編寫單元測試**：
   - 要求 Copilot Chat 產生測試案例：
     ```
     為我們剛剛建立的 calculatePercentage 函式編寫單元測試。
     ```

4. **執行測試**：
   - 執行：
     ```
     npm test calculatePercentage.test.js
     ```

5. **偵錯並反覆改進**：
   - 使用 Copilot Chat 疑難排解任何失敗的測試：
     ```
     這個測試為什麼會失敗？我該如何修正它？
     ```

---

## 任務 3：重構並新增註解

### 目標
透過新增完善的註解並遵循命名慣例，提高程式碼可讀性。

### 步驟

1. **找到已修改的檔案**：
   - 使用 `@workspace` 尋找已變更的檔案：
     ```
     @workspace，到目前為止，我為此任務修改了哪些檔案？
     ```

2. **新增註解**：
   - 要求 Copilot Chat 新增解釋性註解：
     ```
     為以下檔案新增完善的註解，解釋每段程式碼的作用。
     ```

3. **根據命名慣例重構**：
   - 根據需要更新為 camelCase 或其他命名慣例。

---

## 任務 4：部署和使用

### 目標
在一個獨立的 JavaScript 檔案中示範 `calculatePercentage` 的功能。

### 步驟

1. **建立使用端檔案**：
   - 前往儲存庫根目錄。
   - 建立 `consumeCalculatePercentage.js`。

2. **匯入函式**：
   ```javascript
   const { calculatePercentage } = require('./path/to/utilities');
   ```

3. **編寫範例案例**：
   ```javascript
   console.log('範例 1：', calculatePercentage(50, 100)); // 預期輸出：50
   console.log('範例 2：', calculatePercentage(23, 0));  // 預期輸出：0
   console.log('範例 3：', calculatePercentage(7, 20));  // 預期輸出：35
   ```

4. **執行檔案**：
   ```
   node consumeCalculatePercentage.js
   ```

5. **為檔案撰寫文件**：
   - 新增一個解釋其用途的註解區塊：
     ```javascript
     /**
      * 這是一個使用 calculatePercentage 實用函式的簡單示範檔案。
      * 它透過基本案例展示該函式的功能。
      */
     ```

6. **增強示範**：
   - 使用 Copilot Chat 取得建議並進行重構。
   - 也可以新增錯誤處理：
     ```javascript
     try {
       console.log('範例 4：', calculatePercentage('invalid', 20));
     } catch (error) {
       console.error('錯誤：', error.message);
     }
     ```

---

## 總結

本示範展現了 GitHub Copilot Chat 在實作、測試和記錄可重複使用之實用函式方面的強大能力。按照這些步驟操作，你將能夠：
- 開發整潔且易於維護的程式碼。
- 利用 AI 簡化開發流程。
- 透過全面的測試和文件確保功能可靠。

### 資源
- [PowerBI JavaScript 儲存庫](https://github.com/microsoft/PowerBI-JavaScript)
- [Jest 文件](https://jestjs.io/docs/getting-started)
