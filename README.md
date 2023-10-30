# Predict Clicked Ads Customer Classification by using Machine Learning


Dataset : Clicked Ads Data Provided by Rakamin Academy 
<br>
Tools : Jupyter Notebook 
<br>
Programming Language : Python
<br>
Libraries: Pandas, Numpy, Shap, Yellowbrick, Matplotlib, Seaborn
<br>

## Project Background
<div align="justify">  An Indonesian Digital Marketing Consultant Company wants to see the effectivity of advertisements they used in increasing revenue. This project is performed to gain insight of customer behaviour from Data Exploration and create machine learning model to help increasing company's revenue and also create recommendations to build strategy for the marketing team. </div>

## Exploratory Data Analysis
Dataset consisted of 1000 rows and 11 features, 6 categoric & 5 numeric features.

### I. Univariate Analysis
1. Features Distribution
<p align="center">
  <img src= "https://github.com/jedijm/Predict-Clicked-Ads-Customer-Classification/blob/main/asset/histplot.png"> <br>
Fig 1. Features Distribution
</p>

2. `Male`, `Clicked on Ads`, `Category` Distribution
<p align="center">
  <img src= "https://github.com/jedijm/Predict-Clicked-Ads-Customer-Classification/blob/main/asset/category.png"> <br>
Fig 2. Features Distribution
</p>

**Key Takeaways** <br>
1. Most of the numeric features are slightly skewed <br>
2. There are outliers in Area Income feature <br>
3. Clicked on Ad (target feature) is balanced <br>

### II. Bivariate Analysis
1. Boxplot Bivariate Features Distribution
<p align="center">
  <img src= "https://github.com/jedijm/Predict-Clicked-Ads-Customer-Classification/blob/main/asset/boxplot_bivariate.png"> <br>
Fig 3. Boxplot Distribution
</p>

2. KDE Plot Bivariate Features Distribution
<p align="center">
  <img src= "https://github.com/jedijm/Predict-Clicked-Ads-Customer-Classification/blob/main/asset/kdeplot.png"> <br>
Fig 4. KDE Plot Bivariate Features Distribution
</p>

**Key Takeaways** <br>
1. Daily Time Spent on Site <br>
Customer yang menghabiskan waktu lebih sedikit di site (< 60 menit) cenderung melakukan klik pada iklan. <br>
2. Daily Internet Usage <br>
Customer dengan pemakaian internet lebih rendah cenderung melakukan klik pada iklan. <br>
3. Age <br>
Customer dengan umur lebih tua lebih cnederung melakukan klik pada iklan <br>

3. Heatmap Correlation
<p align="center">
  <img src= "https://github.com/jedijm/Predict-Clicked-Ads-Customer-Classification/blob/main/asset/heatmap.png"> <br>
Fig 5. Heatmap Correlation
</p>

## Data Pre-Processing

Table 1. Data Pre-Processing Treatment <br>
**No**  |     **Treatment**      |    **Findings**     |    **Actions**     |
:-----: |    ----------------    |    ------------     |--------------------|
1 |   Handling Missing Values    |    Null Values are identified in few features : <br> 1. `Daily Time Spent on Site` <br> 2. `Area Income` <br> 3. `Daily Internet Usage` <br> 4. `Male`    |- Replacing Null with Mode value in `Male` <br> - Replacing Null with Median value in `Daily Time Spent on Site`, `Area Income`, `Daily Internet Usage`|
2 |   Handling Irrelevant Data     |    - Data type of `Timestamp` is object <br> - `Unnamed: 0` is not relevant |- Convert `Timestamp` to datetime data type <br> - Drop `Unnamed: 0` feature |
3 |    Duplicated Data    | - | - |
4 |  Feature Extraction | `Timestamp` is extractable | Extract `Timestamp` to `Year`, `Week`, `Day`, `Hour` |
5 | Feature Encoding | `Clicked on Ad`, `Male`, `Category` can be encoded | - `Clicked on Ad`, `Male` encoded to 1 & 0 <br> - `Category` encoded with pd.get_dummies |

1. Pre-processed Dataframe for Model
<p align="center">
  <img src= "https://github.com/jedijm/Predict-Clicked-Ads-Customer-Classification/blob/main/asset/df_model.png"> <br>
Fig 6. Pre-processed Dataframe
</p>


 ## Data Modelling
 

