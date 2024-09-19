
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

### Original Data Files

- **PLACES__County_Data__GIS_Friendly_Format___2023_release_20240909.csv**: Health data, including various health outcomes for different counties.
- **SDOH_Measures_for_County__ACS_2017_2021.csv**: Social determinants of health, including factors like education and poverty levels.
- **sdoh_measures_key.csv**: Key file for linking data across datasets.
- **food_access.csv**: Data on food access and availability, including the distance to food sources.

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

