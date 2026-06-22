# Final-Individual-Project

## Analysis of the Difference between Physical Activity Frequency and BMI in Adolescents  
## 青少年運動頻率與 BMI 之差異分析


## Student Information / 學生資訊

Name / 姓名: 楊書雅  
Student ID / 學號: 111A50012  
Class / 班級: 工管三乙  


---

## Project Repository / 專案連結

GitHub:

https://github.com/.....


## Presentation Video / 報告影片

YouTube:

https://youtube.com/.....


---

# Project Overview / 專案介紹

This project uses the CDC Youth Risk Behavior Survey (YRBS) 2007 dataset to investigate whether physical activity frequency affects adolescent BMI.

本研究使用美國 CDC 2007 年青少年健康調查資料（YRBS_2007），探討不同運動頻率是否會造成青少年 BMI 的顯著差異。


Statistical workflow:

Research Question → Data Preparation → Statistical Analysis → Result → Interpretation

分析流程：

研究問題 → 資料處理 → 統計分析 → 結果 → 解釋


---

# Research Question / 研究問題

Do adolescents with different physical activity levels have significantly different average BMI values?

不同運動程度的青少年，其平均 BMI 是否存在顯著差異？


---

# Dataset / 資料集

Dataset:

CDC Youth Risk Behavior Survey 2007 (YRBS_2007.csv)


Original data:

14,041 records


After cleaning:

12,894 valid samples


---

# Variables / 變數定義


## Dependent Variable (Y) / 應變數

BMI (Body Mass Index)

Calculated by:

Weight(kg) / Height(m)^2


Type:

Continuous variable / 連續型變數


---

## Independent Variable (X) / 自變數

Physical Activity Frequency

Original variable:

`PhysicalActivity5OrMoreDays`


Recoded into:


| Group | Days of Exercise |
|-|-|
| Low | 0-2 days |
| Moderate | 3-4 days |
| High | 5-7 days |


---

# Data Processing / 資料處理

Steps:

1. Load raw dataset  
2. Remove missing values  
3. Calculate BMI  
4. Recode exercise frequency into three groups  


處理流程：

1. 讀取原始資料  
2. 移除缺失值  
3. 計算 BMI  
4. 將運動天數重新分類為三組


---

# Statistical Method / 統計方法

## One-way ANOVA

Hypothesis:

H0: Mean BMI values are equal among groups.

H1: At least one group has different BMI.


模型：
