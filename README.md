# Life-Expectancy-Multilinear-Regression-Model-Project
## Project Overview and Objective
The objective of this project is to build and optimize multiple linear regression models to predict life expectancy using socioeconomic and health-related factors. Through data preprocessing, feature selection, cross-validation, and PCA(Principal Component Analysis), the project evaluates different modeling approaches to identify a model that balances predictive accuracy and simplicity. 

## Dataset information

The dataset is sourced from the World Health Organization(WHO) and United Nations(UN).
It consists of 2929 records with 22 columns, categorized as follows:

#### **Demographic Factors**
| Variable | Description |
|---|---|
| **Country** | Name of country |
| **Year** | The year the data was recorded |
| **Status** | Developed or developing country |
| **Population** | Country population |

#### **Health-related factors:**
| Variable | Description |
|---|---|
| **Life Expectancy(The target variable)** | Average life expectancy of the population |
| **Adult Mortality** | Adult mortality rate |
| **Infant Deaths** | Number of infant deaths |
| **Hepatitis B** | Hepatitis B (HepB) immunization coverage among 1-year-olds (%) |
| **Measles** | Number of reported measles cases |
| **BMI** | Average Body Mass Index of the entire population |
| **Under-five deaths** | Number of deaths of children under five |
| **Polio** | Polio (Pol3) immunization coverage among 1-year-olds (%) |
| **Diphtheria** | Diphtheria tetanus toxoid and pertussis (DTP3) immunization coverage among 1-year-olds (%) |
| **HIV/AIDS** | Deaths per 1000 live births due to HIV/AIDS (ages 0-4 years) |
| **Thinness 1-19 years** | Prevalence of thinness among children and adolescents (ages 1-19 years) (%) |
| **Thinness 5-9 years** | Prevalence of thinness among children (ages 5-19 years) (%) |

#### **Socioeconomic factors:**
| Variable | Description |
|---|---|
| **Percentage Expenditure** | Health expenditure in absolute terms (possibly dollars per capita). Note: Incorrectly labeled in the dataset as "percentage of GDP per capita" |
| **Total Expenditure** | General government expenditure on health as a percentage of total government expenditure (%) |
| **GDP** | Gross Domestic Product per capita (in USD) |
| **Income Composition of Resources** | Human Development Index in terms of income composition of resources (index ranging from 0 to 1) |
| **Schooling** | Average number of years of schooling (years) |

#### **Lifestyle Factors**
| Variable | Description |
|---|---|
| **Alcohol** | Alcohol consumption |

## Methodology used
### 1. Data Preprocessing
- Cleaned and standardized column names.
- Removed observations with missing life expectancy values.
- Converted unrealistic zero values into missing values where appropriate.
- Applied log transformations to selected skewed variables.
- Encoded the categorical `Status` variable as a dummy variable.
- Handled missing values using forward/backward filling and K-Nearest Neighbors (KNN) imputation.
- Standardized numerical features before KNN imputation and PCA.

### 2. Multiple Linear Regression
- Built multiple linear regression models to predict life expectancy.
- Evaluated model performance using R², RMSE, F-statistics, and residual analysis.

### 3. Model Validation
- Applied 5-fold cross-validation with repeated train-validation splits to evaluate model performance more reliably.
- Compared models primarily based on cross-validation RMSE and R².

### 4. Feature Selection
Two feature-selection approaches were explored for the non-PCA model:
- **Comprehensive Selection:** Evaluated combinations of highly correlated predictors.
- **Progressive Selection:** Added predictors sequentially based on improvements in cross-validation RMSE.

### 5. Principal Component Analysis (PCA)
- Applied PCA to transform the original predictors into uncorrelated principal components.
- Compared different numbers and combinations of principal components to identify an optimized PCA-based regression model.

### 6. Model Comparison
- Compared the optimized regression models with and without PCA based on predictive performance and model complexity.

## Result
