# Academic References: Recoding Rules & Data Cleaning Protocols
## Standardization for Two-Proportion Asymptotic Inference

### 🛠️ 1. Binary Standardization Rule / 二分變數標準化規範
To satisfy the rigorous assumptions of the independent Two-Proportion $z$-test, all analytical variables are strictly dichotomized following the explicit project instruction protocol:
* **1 = Success / Yes / Exposed Group (高風險暴露組)**
* **0 = Failure / No / Comparison Group (低風險對照組)**

### 📝 2. Explicit Recoding Dictionary / 變數轉換對照表

| Target Variable | Original Variable / Codes | Analytical Mapping | Code Definition |
| :--- | :--- | :--- | :--- |
| **`Sad_Binary`** (Response) | Code 1<br>Code 2<br>Codes 7, 8, 9, Blank | **1**<br>**0**<br>*Dropped* | Yes (Sad/Hopeless Feelings)<br>No (No Sadness)<br>Missing / Invalid Values |
| **`Sex_Label`** (Predictor 1) | Code 2 (Female)<br>Code 1 (Male)<br>Code Blank | **"Female"**<br>**"Male"**<br>*Dropped* | Group 1 for $Z$-test directional alignment<br>Group 2 for $Z$-test directional alignment<br>Missing / Invalid Values |
| **`Safety_Binary`** (Predictor 2) | Codes 2, 3, 4, 5 (1+ Days)<br>Code 1 (0 Days)<br>Codes 7, 8, Blank | **1**<br>**0**<br>*Dropped* | Unsafe / Missed school due to fear<br>Safe / Zero days missed<br>Missing / Invalid Values |
| **`Alcohol_Binary`** (Predictor 3) | Codes 2, 3, 4, 5, 6, 7 (1+ Days)<br>Code 1 (0 Days)<br>Codes 9, Blank | **1**<br>**0**<br>*Dropped* | Current Alcohol User<br>Non-User / Abstinent<br>Missing / Invalid Values |

### ⚠️ 3. Missing Value Handling & Sample Constraints / 缺失值與樣本限制
* **Listwise Deletion**: Any observation containing missing, invalid, or skipped data codes (e.g., code 7 for unknown sex or code 9 for unknown drinking frequency) is completely purged from that specific sub-analysis stratum.
* **Causal Escapement Boundary**: Recoding structure establishes cross-sectional associations at a static temporal horizon (2007). It does not imply chronological or causal precedence.
