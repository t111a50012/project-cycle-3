# Academic References: Variable Definitions & Benchmarks
## Data Source: CDC YRBS 2007 (Youth Risk Behavior Surveillance System)

### 📋 1. Response Variable / 依變量定義
* **Variable Name / 變數名稱**: `SadOrHopeless` (Recoded to `Sad_Binary` in analytical model)
* **Survey Question / 原始問句**: "During the past 12 months, did you ever feel so sad or hopeless almost every day for two weeks or more in a row that you stopped doing some usual activities?"
* **Response Scale / 原始量尺**: Code 1 = Yes, Code 2 = No, Codes 7/8/9/Blank = Missing data.
* **Target Population Benchmark / 母體基準盛行率**: The aggregate raw baseline sadness prevalence across the entire valid sample is approximately **28.52%**.

### 🧬 2. Stratified Grouping Variables / 分層自變量定義與基準值

#### Stratum 1: Biological Sex / 生理性別分歧
* **Variable Name / 變數名稱**: `WhatIsYourSex` (Mapped to `Sex_Label` / `Sex_Binary`)
* **Survey Question / 原始問句**: "What is your sex?"
* **Baseline Stratum Benchmarks / 分層群體盛行率基準**:
  * **Group 1 (Female)**: Valid sample size $N = 4,480$. Sadness prevalence $\hat{p} = \mathbf{32.21\%}$.
  * **Group 2 (Male)**: Valid sample size $N = 4,925$. Sadness prevalence $\hat{p} = \mathbf{19.51\%}$.
  * *Statistical Boundary*: The **-12.70%** net difference aligns with the directional $Z$-score of -13.9821.

#### Stratum 2: Institutional School Safety / 校園安全知覺
* **Variable Name / 變數名稱**: `Safety_Binary` (Derived from `Code 2` vs `Code 1` missed school logic)
* **Survey Question / 原始問句**: "During the past 30 days, on how many days did you not go to school because you felt you would be unsafe at school or on your way to or from school?"
* **Baseline Stratum Benchmarks / 分層群體盛行率基準**:
  * **Group High (Unsafe / Code 2)**: Missed school 1+ days due to safety concerns. Sadness prevalence $\hat{p} = \mathbf{51.09\%}$.
  * **Group Low (Safe / Code 1)**: Missed school 0 days. Sadness prevalence $\hat{p} = \mathbf{25.40\%}$.
  * *Statistical Boundary*: Yields a **25.69%** net risk differential ($Z = 9.5657$).

#### Stratum 3: Risk Alcohol Consumption / 風險飲酒行為
* **Variable Name / 變數名稱**: `Alcohol_Binary` (Derived from current alcohol use frequency)
* **Survey Question / 原始問句**: "During the past 30 days, on how many days did you have at least one drink of alcohol?"
* **Baseline Stratum Benchmarks / 分層群體盛行率基準**:
  * **Group High (Current User / Code 2)**: Drank alcohol 1+ days in the past month. Sadness prevalence $\hat{p} = \mathbf{34.23\%}$.
  * **Group Low (Non-User / Code 1)**: Drank alcohol 0 days. Sadness prevalence $\hat{p} = \mathbf{23.01\%}$.
  * *Statistical Boundary*: Yields an **11.23%** net risk elevation ($Z = 11.1147$).
