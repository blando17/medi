# Medical Insurance Cost Prediction 

This project develops a predictive model using linear regression to estimate individual medical insurance costs based on various personal and health-related attributes.

##  Dataset

The dataset used is `insurance.csv`, containing **1,338 rows** and the following features:

### Features:
- `age`: Age of the person
- `sex`: Gender (male/female)
- `bmi`: Body Mass Index
- `children`: Number of children covered by health insurance
- `smoker`: Smoking status (yes/no)
- `region`: Residential region in the US
- `charges`: Medical insurance cost (target)

## ⚙️ Workflow

### 1. **Data Collection**
- Loaded the CSV file using `pandas`
- Verified there were no missing values

### 2. **Exploratory Data Analysis**
- Statistical summaries using `.describe()`
- Plotted distributions for:
  - Age
  - BMI
  - Number of children
  - Charges
- Count plots for categorical variables:
  - `sex`, `smoker`, and `region`

### 3. **Data Preprocessing**
- Label encoding:
  - `sex`: male = 0, female = 1
  - `smoker`: yes = 0, no = 1
  - `region`: southeast = 0, southwest = 1, northeast = 2, northwest = 3
- Split data into:
  - Features (`X`)
  - Target (`y`: insurance `charges`)

### 4. **Model Training**
- Used **Linear Regression** model from scikit-learn
- Trained on 80% of the data (`train_test_split`)

### 5. **Evaluation**
- **R² score on training data**: 0.75
- **R² score on test data**: 0.74
- Indicates a strong linear relationship and decent generalization

### 6. **Prediction System**
- Built a system to predict insurance cost for new user input
- Example:
  ```python
  input_data = (46, 1, 33.44, 1, 1, 0)
  prediction = model.predict([input_data])
