
# Physical and Social Predictors of Health

## Project Description

The **Physical and Social Predictors of Health** project explores the relationship between various social determinants of health (SDOH), food access, physical symptoms, and health outcomes. The goal is to identify multicollinearity among predictors, uncover the strongest correlations, and build machine learning models to analyze how these social factors contribute to different health conditions. The project leverages data on education, poverty, housing, food access, and health screenings to predict conditions such as heart disease, diabetes, and cancer.

---

![image](https://github.com/user-attachments/assets/20c50957-37c7-49c6-b523-0d68bc9b9666)


## Table of Contents

1. [Installation](#installation)
2. [Data](#data)
3. [Key Scripts](#key-scripts)
4. [Analysis and Machine Learning Models](#analysis-and-machine-learning-models)
5. [Results](#results)
6. [Contributing](#contributing)
7. [License](#license)

---

## 1. Installation

### Clone the Repository:

```bash
git clone https://github.com/EricCroston/Physical_Social_Health_Predictors.git
cd Physical_Social_Health_Predictors
```

### Create a Virtual Environment with the necessary dependencies

## 2. Data

This project utilizes several datasets on social determinants of health (SDOH) and health outcomes. The key datasets include:

PLACES: County Data 2023 release : United States, state and county level
"This dataset contains model-based county-level estimates in GIS-friendly format. PLACES covers the entire United States—50 states and the District of Columbia—at county, place, census tract, and ZIP Code Tabulation Area levels. It provides information uniformly on this large scale for local areas at four geographic levels. Estimates were provided by the Centers for Disease Control and Prevention (CDC), Division of Population Health, Epidemiology and Surveillance Branch. Project was funded by the Robert Wood Johnson Foundation in conjunction with the CDC Foundation. Data sources used to generate these model-based estimates are Behavioral Risk Factor Surveillance System (BRFSS) 2021 or 2020 data, Census Bureau 2021 or 2020 county population estimates, and American Community Survey (ACS) 2017–2021 or 2016–2020 estimates. The 2023 release uses 2021 BRFSS data for 29 measures and 2020 BRFSS data for 7 measures (all teeth lost, dental visits, mammograms, cervical cancer screening, colorectal cancer screening, core preventive services among older adults, and sleeping less than 7 hours) that the survey collects data on every other year. These data can be joined with the census 2020 county boundary file in a GIS system to produce maps for 36 measures at the county level. An ArcGIS Online feature service is also available for users to make maps online or to add data to desktop GIS software."
https://data.cdc.gov/500-Cities-Places/PLACES-County-Data-GIS-Friendly-Format-2023-releas/7cmc-7y5g/about_data
http://www.cdc.gov/nccdphp/dph/

US Food Access https://www.kaggle.com/datasets/mexwell/us-food-access?select=food_access.csv

Lung Cancer Data: https://www.kaggle.com/datasets/nancyalaswad90/lung-cancer/data

Heart Attack Data: https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset/data

![image](https://github.com/user-attachments/assets/bfc33312-afa3-40ed-a670-45b7d00ce2c7)

Healthy People 2030, U.S. Department of Health and Human Services, Office of Disease Prevention and Health Promotion. Retrieved [date graphic was accessed], from https://health.gov/healthypeople/objectives-and-data/social-determinants-health

Social Determinants Of Health by County 2017-2021: 
https://data.cdc.gov/500-Cities-Places/SDOH-Measures-for-County-ACS-2017-2021/i6u4-y3g4/about_data

### Original Data Files

- **PLACES__County_Data__GIS_Friendly_Format___2023_release_20240909.csv**: Health data, including various health outcomes for different counties.
- **SDOH_Measures_for_County__ACS_2017_2021.csv**: Social determinants of health, including factors like education and poverty levels.
- **sdoh_measures_key.csv**: Key file for linking data across datasets.
- **food_access.csv**: Data on food access and availability, including the distance to food sources.
- **heart_attack_analysis.csv**: Binary data for heart attack incidents, used to create the function. Kaggle source
- **survey_lung_cancer.csv**: Binary data for lung cancer diagnosis and symptoms. Kaggle source

### SQL Input Files

- **health_data.csv**: Contains health outcome variables (e.g., diabetes, cancer).
- **sdoh_measures.csv**: Contains social determinants of health (e.g., poverty rate, unemployment).
- **food_access.csv**: Contains food accessibility measures such as the distance to grocery stores.
- **county_key.csv**: Mapping data for linking social and health data to county FIPS codes.

### SQL Output Files

- **CANCER_sdoh_access.csv**
- **CHD_sdoh_access.csv**
- **DIABETES_sdoh_access.csv**
- **JOINED_Data_for_sdoh.csv**

### Data Processing

Data is processed using scripts to:

- Handle missing data.
- Merge datasets based on `CountyFIPS`.
- Normalize/standardize the data for machine learning.

---

## 3. Key Scripts

### `calculate_vif.py`

- Calculates the Variance Inflation Factor (VIF) for SDOH features to identify multicollinearity.
- Outputs a bar plot of features with high multicollinearity.

### `train_model.py`

- Builds and trains a neural network using different activation functions and optimizers.
- Incorporates dropout and regularization techniques to prevent overfitting.
- Outputs model accuracy, loss, and mean absolute error (MAE).

### `correlation_analysis.py`

- Calculates Pearson correlation between health outcomes and SDOH features.
- Generates scatter plots, bar charts, and correlation matrices to visualize the strongest relationships.

### `data_preprocessing.py`

- Handles data cleaning, scaling, and feature engineering for model preparation.

---

## 4. Analysis and Machine Learning Models

### Machine Learning Models

The primary machine learning model used in this project is a **neural network**, which includes:

- **Activation functions**: `relu`, `leaky_relu`, `elu`, `prelu`, `swish`.
- **Optimizers**: `Adamax`, `RMSprop`, `SGD`.
- **Regularization**: Dropout to prevent overfitting.

### Multicollinearity Analysis

- The **Variance Inflation Factor (VIF)** was used to detect multicollinearity in SDOH features.

### Correlation Analysis

- Pearson correlation coefficients were calculated to find relationships between health outcomes and SDOH features.
- Strong correlations were highlighted in scatter plots and bar charts.

---

## 5. Results

### Key Findings

- **Strong Predictors**: Features such as **POV150 (Poverty)** and **REMNRTY (Minority Population)** were highly correlated with certain health outcomes (e.g., diabetes, heart disease).
- **Multicollinearity**: High multicollinearity was observed in certain features, such as **POV150**, which required feature selection techniques like regularization or combining features.
- **Model Performance**: Neural networks trained with regularization techniques performed well in predicting health outcomes, reducing overfitting.

### Visualizations

- **Correlation Bar Graphs**: Shows the strongest correlations between SDOH and health outcomes.
- **Scatter Plots**: Highlights significant relationships between social factors and health outcomes.

![image](https://github.com/user-attachments/assets/8f68b349-db22-4970-bd5b-25029539fd37)

![image](https://github.com/user-attachments/assets/2824dcba-788d-4c79-8fa7-2fe9ae8394cb)

- **VIF Bar Chart**: Displays multicollinearity in social determinant features.

![image](https://github.com/user-attachments/assets/c96e7380-812e-45d5-ba9e-54451ea964c5)

- **Optimization Chart**: Displays the performance of machine learning model using different Optimizers and Activation Fuctions

![image](https://github.com/user-attachments/assets/3dbc0335-60ac-427b-bd53-15170a25d2da)


- **Feature Importance**: Shows what SDOH features were most and least important in machine learning models used

![image](https://github.com/user-attachments/assets/fe7c0ab3-c695-48af-b394-35b537508714)


- **Tableau Story**: Diplays maps comparing SDOH and Health Outcomes and Interactive Visualization
https://public.tableau.com/views/SDOH_17267735512090/SDOHFoodHealthOutcomes?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

![image](https://github.com/user-attachments/assets/9a50d2a9-ef20-4b20-b7de-34bf8aa091c2)

![image](https://github.com/user-attachments/assets/16abff6f-1e88-4070-bfd6-068b28c4a051)

