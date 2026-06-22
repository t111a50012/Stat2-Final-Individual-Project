# Statistics Practicum Final Individual Project / 統計實習期末個人專題


## Analysis of the Difference between Physical Activity Frequency and BMI in Adolescents   
## 青少年運動頻率與 BMI 之差異分析

## 1. Student Information / 學生資訊
* **Name (姓名):** 楊書雅 (Shu-Ya Yang)
* **Student ID (學號):** 111A50012
* **Class (班級):** 工管三乙

---

## 2. Core Links / 專案核心連結
* **Project Repository (GitHub 儲存庫):** https://github.com/.....
* **Presentation Video (YouTube 簡報影片):** https://youtube.com/.....

---

## 3. Project Workflow & Empirical Data / 專案核心架構與數據呈現

### 📌 Research Question / 研究問題
* Do U.S. adolescents with different levels of weekly physical activity (Low, Moderate, High) have significantly different average Body Mass Index (BMI) values?
  
* 不同體育活動參與程度（低、中、高運動量組）的美國青少年，其平均身體質量指數（BMI）是否存在顯著的統計學差異？

---

### 📌 Data Preparation & Variable Definitions / 資料準備與變數定義

#### 1. Dataset & Sample Size / 資料集與樣本數
* Based on the U.S. CDC 2007 Youth Risk Behavior Survey (`YRBS_2007.csv`), listwise deletion was applied to handle missing values, retaining a final valid sample size of 12,894 records.
  
* 採用美國 CDC 2007 年青少年危險行為調查（`YRBS_2007.csv`）資料集，透過嚴格剔除缺失值（Listwise Deletion）進行資料處理，最終保留 12,894 筆有效分析樣本。

#### 2. Operational Definitions of Variables / 變數之操作化定義
* **Dependent Variable (Y, 應變數): `BMI` (Body Mass Index)**
  * A continuous numeric variable representing weight status. Calculated using the formula: $\text{Weight (kg)} / \text{Height (m)}^2$, derived from original survey items `HowMuchDoYouWeighWithoutShoesInKG` and `HowTallAreYouWithoutShoesInMeters`.
    
  * 連續型數值變數，用以衡量青少年體態與肥胖程度。計算公式為：體重除以身高的平方，數據源自原始問卷欄位 `HowMuchDoYouWeighWithoutShoesInKG` 與 `HowTallAreYouWithoutShoesInMeters`。
    
* **Independent Variable (X, 自變數): `Activity_Group` (Physical Activity Level)**
  * An ordinal categorical variable derived from the original continuous survey item `PhysicalActivity50rMoreDays` (the number of days with at least 60 minutes of physical activity in the past 7 days), recoded into three explicit empirical groups:
    1. `Low (0–2 days)`: Sedentary or low-activity lifestyle (0 to 2 days of exercise per week).
    2. `Moderate (3–4 days)`: Baseline active lifestyle (3 to 4 days of exercise per week).
    3. `High (5–7 days)`: Highly active lifestyle meeting advanced health guidelines (5 to 7 days of exercise per week).
       
  * 順序型類別變數，由原始連續型欄位 `PhysicalActivity50rMoreDays`（過去7天內，運動累積達60分鐘以上的天數）重新編碼而成，分為三個明確的實證群組：
    1. `Low (0-2天)`: 久坐或低活動量生活型態（每週運動 0 至 2 天）。
    2. `Moderate (3-4天)`: 具備基礎活動量生活型態（每週運動 3 至 4 天）。
    3. `High (5-7天)`: 高活動量且符合進階健康指引之生活型態（每週運動 5 至 7 天）。

#### 【Descriptive Statistics Table / 描述性統計摘要表】
| Activity Group (自變數分組) | Sample Count ($N$, 樣本數) | BMI Mean (平均數) | BMI Std (標準差) |
| :--- | :---: | :---: | :---: |
| **High (5–7 days)** | 5,461 | 23.45 | 4.56 |
| **Moderate (3–4 days)** | 2,789 | 23.91 | 5.05 |
| **Low (0–2 days)** | 4,644 | 24.12 | 5.39 |

---

### 📌 Statistical Method / 統計方法
* * **Omnibus Test:** One-way Analysis of Variance (One-way ANOVA) to test the overall null hypothesis ($H_0: \mu_{\text{Low}} = \mu_{\text{Moderate}} = \mu_{\text{High}}$) that all group means are equal.
  * **Post-hoc Test:** Tukey's Honestly Significant Difference (Tukey's HSD) for pairwise multiple comparisons to locate specific group differences while controlling the family-wise Type I error rate at $\alpha=0.05$.


* * **整體檢定:** 單因子變異數分析（One-way ANOVA），用以檢定整體虛無假設，即所有運動組別的平均 BMI 是否相等。
  * **事後檢定:** Tukey's HSD 事後多重比較檢定，在嚴格控制家庭期型一錯誤率（p < 0.05）的前提下進行兩兩成對對比，精準定位組別間的具體差異。

---

### 📌 Results / 結果呈現

#### 1. Overall Test: One-way ANOVA Table / 整體檢定：變異數分析表
| Source of Variation (變異來源) | Sum of Squares ($SS$, 平方和) | Degrees of Freedom ($df$, 自由度) | $F$-statistic ($F$ 值) | $p$-value ($p$ 值) |
| :--- | :---: | :---: | :---: | :---: |
| **Group (組間效應)** | 1,153.139 | 2.0 | **23.237** | **$8.442 \times 10^{-11}$** |
| **Residual (組內殘差)** | 319,859.363 | 12,891.0 | — | — |
* *Decision: Since the p-value is far less than 0.05, we successfully reject the null hypothesis ($H_0$). / 統計決策：因 $p$ 值遠小於 0.05，成功拒絕虛無假設。*

#### 2. Pairwise Comparisons: Tukey's HSD Table / 兩兩比較：事後檢定表
| Comparison Pair (兩兩對比組別) | Mean Diff (均值差) | Adjusted $p$-value (調整後 $p$ 值) | 95% CI (信心區間)  | Reject $H_0$ (具顯著差異) |
| :--- | :---: | :---: | :---: | :---: |
| **High** vs **Low** | 0.664 | 0.000 ( < 0.001 ) | [  0.431, 0.897  ] | **True (是)** |
| **High** vs **Moderate** | 0.451 | 0.0003 | [  0.179, 0.723 ] | **True (是)** |
| **Low** vs **Moderate** | -0.213 | 0.1745 | [  -0.493, 0.067 ] | **False (否)** |

---

### 📌 Interpretation & Recommendations / 實質詮釋與政策建議

* **Final Results:** The empirical data reveals a critical threshold effect: the `High` activity group (5–7 days) exhibits a significantly lower average BMI than both the `Low` activity group ($\text{meandiff} = 0.664$, $p < 0.001$) and the `Moderate` activity group ($\text{meandiff} = 0.451$, $p < 0.001$). Crucially, there is no statistically significant difference in average BMI between the `Moderate` and `Low` activity groups ($p = 0.1745$). This demonstrates that regular exercise is effective for weight regulation, but **"frequency" is the deciding factor**.
  
* **Core Recommendations:** Exercising only 3–4 days a week yields no statistically distinct benefit over being sedentary in shifting collective BMI. Therefore, public health and school physical education policies must move away from generic "exercise more" slogans and actively implement targeted interventions that encourage adolescents to increase their physical activity to a high frequency of **5–7 days a week** to unlock substantial health and weight-regulation benefits.
    
* **最終結果:** 大數據實證顯示出關鍵的「門檻效應」：`高運動量組 (5-7天)` 的平均 BMI 顯著低於 `低運動量組`（均值差 $= 0.664$，p < 0.001）與 `中運動量組`（均值差 $= 0.451$，p < 0.001）。至關至要的是，`中運動量組 (3-4天)` 與 `低運動量組 (0-2天)` 之間的平均 BMI 在統計上**完全沒有顯著差異**（p = 0.1745）。這證實了規律運動雖能調節體態，但「運動頻率」才是核心決定因素。
  
* **核心建議:** 每週僅運動 3-4 天在現實世界中，與幾乎不運動相比，並未能實質拉低大眾整體平均的 BMI。因此，未來的公共衛生政策與學校體育課程規劃，不應僅停留在「有運動就好」的泛泛口號，而必須制定具體的干預計畫，積極鼓勵並引導青少年將運動頻率提升至**每週 5 至 7 天**的高頻率水平，方能真正發揮維持健康體態與調節體重風險的實質效益。

---

## 4. Repository Structure / 儲存庫目錄分層架構
```text
.
├── data/
│   ├── raw/
│   │   └── YRBS_2007.csv               # Raw dataset / 原始資料
│   └── processed/
│       ├── yrbs_cleaned.csv            # Cleaned data (missing values removed)
│       └── yrbs_recoded.csv            # Final processing with recoded activity groups
├── notebooks/
│   ├── 01_data_check.ipynb             # Step 1: Data checking & recoding
│   ├── 02_eda_anova.ipynb              # Step 2: Exploratory Data Analysis & ANOVA
│   └── 03_inference.ipynb              # Step 3: Tukey's HSD post-hoc test & outputs
├── outputs/
│   ├── figures/
│   │   ├── continuous_histogram.png    # BMI distribution histogram
│   │   ├── behavior_bar_chart.png      # Group sample counts
│   │   └── bmi_activity_boxplot.png    # Final statistical inference boxplot
│   ├── tables/
│   │   ├── eda_summary_table.csv       # Group descriptive statistics
│   │   ├── inference_summary_table.csv # ANOVA summary table
│   │   └── tukey_posthoc_table.csv     # Pairwise Tukey's HSD results table
│   ├── summary/
│       └── final_summary.txt           # Automated statistical text summary
│── report/   
│       └── summary.pdf                 # Final project report summary PDF / 專案總結報告
└── references/
    ├── variable_definitions.md         # Metadata for independent & dependent variables
    ├── recoding_rules.md               # Coding logic (Continuous to ordinal days)
    └── variable_notes.md               # CDC BMI benchmarks & ANOVA assumptions
