# FB Contest Fairness Analyzer (Side Project)

### Facebook 競賽公平性分析與抗灌水抓取工具

## 💡 專案開發動機

本專案源於一次參加 Facebook 社群抽獎競賽的個人經歷。在觀察競賽過程中，發現部分競爭者疑似使用「留言灌水」手段（即極少數帳號短時間內大量重複留言），試圖透過洗版來誤導活動數據，導致競賽失去公平性。

為了驗證這項觀察，我開發了這套 Side Project。透過自動化抓取完整的留言數據，分析「帳號去重後的真實參與人數」，以此識破灌水行為，並量化自己與對手之間的真實數據缺口 (Gap)。

---

## 🛠 我解決了哪些問題？

### 1. 破解 FB 的「留言隱藏機制」

Facebook 預設會隱藏大量重複或長留言。本工具利用 **Selenium** 模擬人工點擊，遞迴式地展開所有「查看更多留言」與「回覆」，確保獲取 100% 的原始樣本。

### 2. 識別「虛假繁榮」 (Anti-Cheating)

* **不重複者分析 (Distinct Count)**：透過 UID 統計，一眼看出哪些貼文是靠少數人「洗出來」的數字。
* **數據透明化**：將原本模糊的社群數據轉化為結構化的 Pandas DataFrame，並計算出真正具有代表性的活動數據。

### 3. 自動化數據對比

* 自動匯出 Excel 報表，直接對比多個目標網址。
* 計算 **Gap** (數據缺口)，輔助評估當時競賽的真實領先/落後幅度。

---

## ⚠️ 專案狀態說明 (Maintenance Note)

> **本專案建置於 2020 年，主要用於個人技術思路與邏輯架構之展示。**
> 由於 Facebook 網頁結構時常更新，本代碼之元素定位 (XPath/CSS Selector) 僅供參考，若需在現行環境執行，可能需針對當前 DOM 結構進行調整。

---

## 🚀 技術棧 (Tech Stack)

* **語言**: Python 3.x
* **核心工具**: Selenium WebDriver, BeautifulSoup4
* **數據分析**: Pandas

---

## ⚙️ 快速測試方式

1. 安裝套件：`pip install pandas selenium beautifulsoup4`
2. 準備與 Chrome 版本一致的 `chromedriver`。
3. 於腳本中輸入 FB 帳密及目標貼文連結。
4. 執行 `fb_contest_analyzer.ipynb` 即可產出分析報表。

---

## 📊 數據分析範例 (Example)

分析結果能清楚顯示：雖然某貼文有 700 多則留言，但去重後的「有效參與者」可能不到一半，藉此識別出灌水帳號。

| Post URL | Total Comments | **Distinct Users (Real)** |
| --- | --- | --- |
| Competitor_Post | 711 | **283** |

---

### 👨‍💻 作者

**Eason**
一位喜歡用自動化工具解決生活瑣事的資深工程師。

