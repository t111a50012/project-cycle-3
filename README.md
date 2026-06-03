# Project Cycle 3: Two-Sample Inference
# 專案循環 3：雙樣本推論

## 👥 Team Information / 小組基本資訊
* **Group Number / 小組組號:** Group 26 
* **Members / 成員姓名:** 111A50012 楊書雅 (Shu-Ya Yang), 113370216 彭佳淳 (Chia-Chun Peng)
  
## Presentation Video
https://youtu.be/lycv5PV_-ss

---

## 🎯 Selected Research Question / 所選的研究問題
Our project is based on the CDC's `YRBS_2007.csv` dataset. We selected **Question 3** and expanded it into an advanced multi-dimensional framework to analyze adolescent mental health across three independent vectors:

本專案基於美國 CDC 的 `YRBS_2007.csv` 數據集，選擇並深入探討**問題 3**。我們將其擴展為一個進階的多維度分析架構，跨越三個獨立向量來研究青少年的心理健康：

* **Project Title / 專案名稱:** An Advanced Multi-Dimensional Comparison of the Proportions of Sad or Hopeless Feelings Among Adolescents
  (多維度族群之青少年悲傷與絕望感比例比較研究)
  
* **Core Research Question / 核心研究問題:** Do the proportions of students who feel sad or hopeless differ significantly across different youth demographic, safety, and behavioral groups?
  
  在不同的青少年人口統計、校園安全與行為風險族群中，感到嚴重悲傷或絕望的學生比例是否存在顯著差異？

---

## 🧪 Variables Definition / 組別變數與反應變數

### 1. Response Variable (Y) / 反應變數
* **Original Column / 原始欄位:** `SadOrHopeless`
* **Binary Recoded Variable / 重編碼二元變數:** `Sad_Binary`
  * **1 (Success / Exposed Group):** Students who felt so sad or hopeless almost every day for 2+ weeks in a row that they stopped doing some usual activities (Original code 1).
    **1 (成功 / 暴露組)：** 過去 12 個月內，幾乎天天感到悲傷或絕望且持續 2 週以上，以致停止日常活動者（原始編碼 1）。
  * **0 (Failure / Comparison Group):** Students without these severe feelings (Original code 2).
    **0 (失敗 / 對照組)：** 無上述嚴重悲傷或絕望感者（原始編碼 2）。

### 2. Grouping Variables (X) / 組別變數
To increase analytical depth, we investigated three independent dimensions:
為了提升分析深度，我們深入研究了三個獨立維度：
* **Dimension 1: Biological Sex (生理性別向量)**
  * Column / 變數: `WhatIsYourSex`
  * Groups / 對比組別: Female (女學生, $N=4,898$) vs. Male (男學生, $N=1,599$)
* **Dimension 2: School Safety (校園安全知覺向量)**
  * Column / 變數: `Safety_Binary` (Recoded from school missing days due to safety concerns / 依安全顧慮缺課天數重編碼)
  * Groups / 對比組別: Unsafe (因安全顧慮缺課 1 天以上之學生) vs. Safe (正常上學之學生)
* **Dimension 3: Behavioral Risk (行為健康風險向量)**
  * Column / 變數: `Alcohol_Binary` (Recoded from current alcohol use days / 依現行飲酒行為天數重編碼)
  * Groups / 對比組別: Current User (現行有飲酒之學生) vs. Non-User (無飲酒之學生)

---

## 🛠️ Statistical Methodology / 使用的方法
We developed a rigorous data science and statistical pipeline:
我們開發了一套嚴謹的資料科學與統計推論管線：

1. **Data Cleaning Protocol / 資料清理協議:** Enforced **Listwise Deletion (`.dropna()`)** on key sub-samples to eliminate missing values and invalid codes, ensuring a synchronized analytical base and exporting the clean data as `yrbs_cleaned.csv`.
   
   針對關鍵欄位執行完全個案剔除法 (`.dropna()`)以排除缺失值與無效代碼，確保分析底冊的同步性，並將乾淨數據導出為 `yrbs_cleaned.csv`。
   
2. **Exploratory Data Analysis / 探索性資料分析:** Aggregated descriptive conditional proportions ($\hat{p}$) and developed a **Multi-Dimensional Matrix Heatmap** to visualize risk hierarchies.

   聚合計算各分層組別的條件觀測比例（$\hat{p}$），並利用**多維度矩陣熱圖**直觀呈現風險強度排序。
   
3. **Inference Method / 推論統計方法:** Executed three independent asymptotic **Two-Proportion z-tests**. We calculated the point estimates, standard errors (SE), Z-statistics, exact p-values, and **95% Confidence Intervals (CI)** to evaluate population-level significance.

   跨三個核心維度執行獨立的**漸進式雙比例 z 檢定**。我們計算了點估計值、標準誤差（SE）、Z 統計量、精確 p 值與 **95% 信賴區間（CI）**，以評估母體層級的顯著性。

---

## 📝 Conclusion / 結論
1. **School Safety as the Strongest Driver / 校園安全為最強風險源:** Dimension 2 carried the heaviest statistical weight. Students who skipped school due to safety concerns showed a staggering sadness prevalence of **51.09%** (compared to **24.57%** for safe students), making it the absolute highest risk point on our heatmap.
   
   `校園安全（維度二）` 展現了最強烈的統計關聯效應。因安全顧慮而缺課的學生，其悲傷絕望盛行率高達 **51.09%**（對比正常學生的 **24.57%**），為全圖表的絕對最高風險點。
   
2. **Structural Gender Divergence / 結構性性別情感分歧:** The two-proportion z-test confirmed that females have a significantly higher sadness prevalence (**32.21%**) than males (**19.51%**), with a net risk differential of **-12.70%** ($Z = -13.98, p < 0.001$). The 95% CI (**$[-14.45\%, -10.96\%]$**) completely excludes zero, indicating a highly stable population variance that supports the "adolescent affective vulnerability theory."
   
   雙比例 z 檢定證實女性青少年的悲傷盛行率（**32.21%**）顯著高於男性（**19.51%**），淨落差達 **-12.70%**（$Z = -13.98, p < 0.001$）。95% 信賴區間（**$[-14.45\%, -10.96\%]$**）完全排除零點，說明此分歧在母體中極其穩固，支持青春期情感脆弱性理論。
   
3. **Behavioral Risk Co-morbidity / 風險行為高度共病:** Current alcohol users experienced a significantly higher proportion of distress (**34.23%**) compared to non-users (**22.56%**).
   現行有飲酒風險行為的群體（**34.23%**）相較於無飲酒群體（**22.56%**），表現出顯著較高的情感絕望傾向。
   
4. **Policy Recommendation / 核心政策建議:** Since school environmental safety carries the most critical statistical impact, public health and educational sectors must prioritize resource allocation to constructing a secure, violence-free campus environment to protect youth mental health.
   
   鑑於校園安全威脅在統計上帶有最沉重的權重，公共衛生與教育部門應優先將資源投入於「建構安全、防範暴力的校園環境」，作為保護青少年心理健康的第一線防禦機制。
