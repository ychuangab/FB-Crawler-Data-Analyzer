# FB Contest Intelligence Analyzer & Competitor Insight

### Facebook 競賽自動化數據爬蟲與競爭者缺口分析工具

## 📖 專案背景

在進行 Facebook 社群行銷活動時，面對數百甚至數千則留言，手動統計不僅耗時且容易出錯。此外，Facebook 預設會隱藏大量留言與回覆，導致難以獲取完整的競爭對手數據。

本專案開發了一套自動化流程，透過 **Selenium** 模擬真實用戶行為，深度抓取動態載入的留言，並利用 **Pandas** 進行數據清洗與「競爭者缺口分析 (Gap Analysis)」，協助決策者快速掌握活動成效與市場競爭現況。

---

## 🚀 核心技術功能

### 1. 深度動態爬蟲 (Deep Web Scraping)

* **自動化模擬登入**：處理 FB 登入驗證流程。
* **遞迴展開機制**：自動偵測並點擊「查看更多留言」、「查看回覆」，確保獲取 100% 的原始留言數據，不受 FB 動態加載限制。
* **非同步等待策略**：優化 `Implicitly Wait` 與 `Sleep` 邏輯，平衡爬取效率與規避平台偵測。

### 2. 數據清洗與反作弊分析 (Data Cleaning & Anti-Cheating)

* **有效參與者過濾**：透過 `Distinct Count` (UID/姓名去重)，過濾重複洗版、惡意灌水的留言，計算「真實有效參與人數」。
* **關鍵字精準對齊**：支援特定 Hashtag 或活動關鍵字偵測（如：`#雨潔我要抽`）。

### 3. 競爭者缺口分析 (Competitor Gap Analysis)

* **Gap 計算**：自動對比自身與多個競爭對手間的留言數差異。
* **實時排名**：將多篇貼文數據進行結構化整合，產出對比報表，直觀顯示數據領先/落後幅度。

---

## 🛠 技術棧 (Tech Stack)

* **語言**: Python 3.x
* **自動化框架**: Selenium WebDriver (Chrome)
* **網頁解析**: BeautifulSoup4, Regex
* **數據處理**: Pandas, NumPy
* **開發工具**: Jupyter Notebook (可擴充為 .py 腳本)

---

## ⚠️ 注意事項 (Maintenance Note)

> **本專案建置於 2020 年，主要用於技術思路與邏輯架構之展示。**
> 由於 Facebook 網頁前端結構與 API 政策隨時間頻繁更迭，部分元素定位 (CSS Selector/XPath) 或爬取邏輯在現行環境下可能需要配合最新版本進行調整。

---

## ⚙️ 快速開始 (Quick Start)

### 1. 環境需求

* 安裝 Google Chrome 瀏覽器。
* 下載與 Chrome 版本相符的 [ChromeDriver](https://chromedriver.chromium.org/downloads)。

### 2. 安裝套件

```bash
pip install pandas selenium beautifulsoup4

```

### 3. 執行參數設定

於 `FB_Crawler_Analysis.ipynb` 中修改以下變數：

```python
login_id = 'your_fb_account'
login_pw = 'your_password'
search_key = '#活動關鍵字'

```

---

## 📊 數據產出示例

分析完成後，程式將自動匯出 Excel 報表，包含以下欄位：

* **CommentCnt**: 原始留言總數
* **Distinct_CommentCnt**: 去重後的有效參與人數
* **Gap**: 與標竿貼文的數據差距

---

## 🛡 免責聲明

本專案僅供技術研究與學術學習使用。請使用者遵循 Facebook 的《服務條款》及相關爬蟲規範（robots.txt），切勿用於商業惡意用途或違反隱私權之行為。

---

### 👨‍💻 作者

**Eason** 資深工程師 | 專注於自動化工具開發、AI 數據整合及系統優化。


