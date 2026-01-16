# FB Contest Data Analyzer & Competitor Insight
### Facebook 競賽數據爬蟲與競爭者分析工具

本專案是一個基於 Python 的自動化工具，旨在解決 Facebook 抽獎活動中「留言統計困難」與「競爭數據不透明」的問題。透過自動化模擬瀏覽器行為，完整展開所有隱藏留言，並進行深度數據清洗與對比分析。

## 🚀 核心功能 (Key Features)
- **自動化模擬登入**：處理 Facebook 登入流程，進入特定活動貼文。
- **動態留言展開 (Recursive Expansion)**：自動偵測並點擊「查看更多留言/回覆」，克服動態載入限制，確保獲取 100% 原始數據。
- **關鍵字過濾與統計**：針對特定抽獎標籤（Hashtag）或關鍵字進行精準統計。
- **競爭者 Gap 分析**：自動計算目標對手與自己的數據差距，並進行排序。
- **異常行為檢測 (Anti-Cheating)**：透過 UID 去重計算「有效參與人數」，識別重複洗版或灌水行為。
- **數據匯出**：自動產出結構化 Excel 報表，方便後續決策參考。

## 🛠 技術棧 (Tech Stack)
- **Language**: Python 3.x
- **Automation**: Selenium WebDriver (Chrome)
- **Parsing**: BeautifulSoup4 (BS4), Regex
- **Data Processing**: Pandas
- **Environment**: Jupyter Notebook / Python Script

## 📁 檔案結構說明
- `main2.ipynb`: 核心腳本，包含自動化爬蟲邏輯與數據處理流程。
- `chromedriver`: Chrome 瀏覽器驅動程式 (需與版本對應)。
- `README.md`: 專案說明文件。

## ⚙️ 安裝與使用 (Setup)
1. **複製專案**
   ```bash
   git clone [https://github.com/您的帳號/FB-Contest-Data-Analyzer.git](https://github.com/您的帳號/FB-Contest-Data-Analyzer.git)
