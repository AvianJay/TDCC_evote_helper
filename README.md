# TDCC Helper Tool

This repository provides tools to assist shareholders with the TDCC electronic voting process, including automated voting and screenshot features.

---

- [TDCC Helper Tool](#tdcc-helper-tool)
  - [English Manual](#english-manual)
    - [Build Command](#build-command)
    - [Usage](#usage)
      - [1. rename\_tool](#1-rename_tool)
      - [2. TDCC\_helper\_tool](#2-tdcc_helper_tool)
  - [中文說明（繁體）](#中文說明繁體)
    - [建置指令](#建置指令)
    - [使用說明](#使用說明)
      - [1. rename\_tool](#1-rename_tool-1)
      - [2. TDCC\_helper\_tool](#2-tdcc_helper_tool-1)


---

## English Manual

### Build Command

```
pyinstaller -F ./TDCC_helper_tool.py
pyinstaller -F ./rename_tool.py
```

---

### Usage

#### 1. rename_tool

**How to use:**
- Double-click the executable or run the script with Python.

**What it does:**
- Moves and renames all PNG files from `./screenshots/{id}/*.png` to `./screenshots/all/*_{id}.png`.
- This helps consolidate screenshots from different shareholder IDs into a single folder, with filenames indicating their original ID.

---

#### 2. TDCC_helper_tool
This program assists shareholders in the TDCC voting process, including automated voting and screenshot features. It helps minority shareholders receive shareholder meeting souvenirs.
**Step-by-step usage:**

1. **Start the program**
   - Double-click the executable or run the script with Python.

2. **If unfinished screenshots are detected**
   - The tool will display:  
     `Last time have unfinished screenshot, do you want to continue? (Y/N) :`
   - If you enter `Y`, it will guide you through completing those screenshots first.

3. **Main menu**
   - The tool will display:
     ```
     (1) all accounts vote+take screenshot
     (2) take screenshot of specific stocks
     (3) exit
     please select:
     ```
   - Enter `1`, `2`, or `3`.

4. **If you select (1) all accounts vote + take screenshot**
   - The tool will check for existing settings. If not found or you choose to reconfigure, you will be prompted:
     - `please enter the run speed (default is 2):`  
       (Enter a number between 1~30; smaller is faster)
     - `please enter the shareholder ID(台灣的身分證字號), one ID per line, end with 'end' :`  
       (Enter each ID, then type `end` to finish)
     - `please enter the default vote option (accept/opposite/abstain):`  
       (Choose one: `accept`, `opposite`, or `abstain`)
     - For manual voting keywords:
       - `please enter the keyword to accept, one keyword per line, end with 'end' :`
       - `please enter the keyword to opposite, one keyword per line, end with 'end' :`
       - `please enter the keyword to abstain, one keyword per line, end with 'end' :`
     - After each section, you will be asked to confirm:
       - `do you want to save the setting?(y/n)?`
       - `do you want to use the above setting?(y/n)?`
   - For each shareholder ID:
     - The tool will automatically log in, vote according to your settings, and take screenshots for each stock.
     - All screenshots are saved in `./screenshots/{id}/`.
   - After all accounts are processed, the tool logs out and closes the browser.

5. **If you select (2) Take screenshot of specific stocks**
   - The tool will prompt:
     - `Please enter the ID number to take screenshots:(-1 to exit)`
     - `Please enter the stock ID to take screenshots, multiple stock IDs should be separated by ",":(-1 to exit)`
   - The tool will log in and take screenshots for the specified stocks.

6. **Exit**
   - Select (3) to exit the program.

**Notes:**
- You can modify voting content at any time; it will not affect your actual voting intent.
- The script is for assistance only and does not take responsibility for any consequences.

---

## 中文說明（繁體）

### 建置指令

```
pyinstaller -F ./TDCC_helper_tool.py
pyinstaller -F ./rename_tool.py
```

---

### 使用說明

#### 1. rename_tool

**使用方式：**
- 直接雙擊執行檔或用 Python 執行腳本。

**功能說明：**
- 將 `./screenshots/{id}/*.png` 目錄下所有 PNG 檔案，移動並重新命名到 `./screenshots/all/` 資料夾，檔名格式為 `*_{id}.png`。
- 方便將不同股東 ID 的截圖集中管理，並保留來源 ID 資訊於檔名。

---

#### 2. TDCC_helper_tool
此程式用於協助股東進行 TDCC 投票，包含自動投票及截圖功能。以幫助零股股東領取股東會紀念品
**操作步驟說明：**

1. **啟動程式**
   - 直接雙擊執行檔或用 Python 執行腳本。

2. **若偵測到上次未完成的截圖**
   - 程式會顯示：  
     `Last time have unfinished screenshot, do you want to continue? (Y/N) :`  
     （上次有未完成的截圖，是否繼續？輸入 Y 繼續）
   - 若輸入 `Y`，會先引導你完成這些截圖。

3. **主選單**
   - 程式會顯示：
     ```
     (1) all accounts vote+take screenshot（所有帳號自動投票並截圖）
     (2) take screenshot of specific stocks（指定股票截圖）
     (3) exit（離開）
     please select:（請選擇）
     ```
   - 輸入 `1`、`2` 或 `3`。

4. **選擇 (1) 所有帳號自動投票並截圖**
   - 程式會檢查設定，若無設定或選擇重新設定，會依序詢問：
     - `please enter the run speed (default is 2):`  
       投票速度（輸入 1~30，數字越小越快）
     - `please enter the shareholder ID(台灣的身分證字號), one ID per line, end with 'end' :`  
       股東身分證字號（每行一個，輸入 end 結束）
     - `please enter the default vote option (accept/opposite/abstain):`  
       預設投票方式（accept=贊成，opposite=反對，abstain=棄權）
     - 關鍵字設定（可選，依序輸入，每行一個，輸入 end 結束）：
       - `please enter the keyword to accept, one keyword per line, end with 'end' :`（贊成關鍵字）
       - `please enter the keyword to opposite, one keyword per line, end with 'end' :`（反對關鍵字）
       - `please enter the keyword to abstain, one keyword per line, end with 'end' :`（棄權關鍵字）
     - 設定完成後會請你確認：
       - `do you want to save the setting?(y/n)?`（是否儲存設定）
       - `do you want to use the above setting?(y/n)?`（是否使用上述設定）
   - 每個股東帳號會自動登入、依設定自動投票，並為每檔股票截圖。
   - 所有截圖會儲存於 `./screenshots/{id}/` 資料夾。
   - 全部完成後會自動登出並關閉瀏覽器。

5. **選擇 (2) 指定股票截圖**
   - 程式會詢問：
     - `Please enter the ID number to take screenshots:(-1 to exit)`  
       輸入股東身分證字號（-1 離開）
     - `Please enter the stock ID to take screenshots, multiple stock IDs should be separated by ",":(-1 to exit)`  
       輸入股票代號（多個用逗號分隔，如 2330,2317，(-1 離開)）
   - 程式會自動登入並為指定股票截圖。

6. **離開程式**
   - 選擇 (3) 離開。

**注意事項：**
- 投票內容可隨時修改，不影響實際投票意願。
- 本工具僅供輔助，使用造成的任何後果請自行負責。

---

如有建議或問題，歡迎於 GitHub 討論區提出。
