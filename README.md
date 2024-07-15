# Crash Data Analysis and Classification using XGBoost, CatBoost, and LightGBM

This project involves the analysis of crash data, focusing on crash hotspots, crash rates by road type and municipality, and the development of classification models to predict injury severity using machine learning algorithms including XGBoost, CatBoost, and LightGBM. 

## Data Description

The dataset used in this project is the Crash Reporting - Drivers Data for Maryland, which can be downloaded from the following link:

[Crash Reporting - Drivers Data](https://data.montgomerycountymd.gov/api/views/mmzv-x632/rows.csv?accessType=DOWNLOAD)

The dataset contains 172,105 rows and 43 columns, including various features related to crashes such as:

- Report Number
- Local Case Number
- Agency Name
- ACRS Report Type
- Crash Date/Time
- Route Type
- Road Name
- Cross-Street Type
- Cross-Street Name
- Off-Road Description
- Speed Limit
- Driverless Vehicle
- Parked Vehicle
- Vehicle Year
- Vehicle Make
- Vehicle Model
- Equipment Problems
- Latitude
- Longitude
- Location
- Injury Severity (target variable)

## Data Preprocessing

The preprocessing steps include:

1. **Handling Missing Values**: 
   - Categorical columns are filled with the mode.
   - Numerical columns are filled with the mean.

2. **Label Encoding**: 
   - Categorical variables are converted into numerical values using `LabelEncoder`.

3. **Feature Scaling**: 
   - Numerical features are scaled using `StandardScaler`.

4. **Class Balancing**:
   - Due to the imbalanced nature of the target variable (Injury Severity), `SMOTE` (Synthetic Minority Over-sampling Technique) is used to balance the classes.

## Exploratory Data Analysis (EDA)

### 1. Crash Hotspots
Using latitude and longitude data, crash hotspots were identified, showing that most crashes occurred in the Washington D.C. area and Baltimore.

### 2. Road Type and Crashes
Crash rates were compared across different types of roads:
- Maryland state roads had the highest number of crashes.
- County roads followed next.
- Interstate roads had the least number of crashes among the top road types.

### 3. Crashes by Municipality
Crashes were examined across different municipalities:
- Rockville had the highest number of crashes.
- Gaithersburg and Takoma Park also had high crash rates.
- Drummond Municipality had the least number of crashes.

## Classification Models

Three machine learning models were used to predict injury severity: XGBoost, CatBoost, and LightGBM.

### XGBoost Model
- **Accuracy**: 84.67%
- **Confusion Matrix**: Shows high precision and recall for all classes, especially for class 0 (no injury).

### CatBoost Model
- **Accuracy**: 87.59%
- **Confusion Matrix**: High precision and recall for all classes, with notable improvement in class 4 (serious injury).

### LightGBM Model
- **Accuracy**: 80.27%
- **Confusion Matrix**: Good performance but slightly lower compared to XGBoost and CatBoost.

## Visualization

Confusion matrices for each model were visualized using heatmaps to understand the performance of the models better.

## Conclusion

This project demonstrates the use of various data preprocessing techniques, exploratory data analysis, and machine learning algorithms to analyze crash data and predict injury severity. The CatBoost model showed the best performance among the three models.

## Dependencies

The project requires the following Python libraries:
- pandas
- numpy
- matplotlib
- seaborn
- sklearn
- xgboost
- catboost
- lightgbm
- imblearn

Ensure all the dependencies are installed before running the analysis.

## How to Run

1. Download the dataset from the provided link.
2. Place the dataset in the `../data/` directory.
3. Run the analysis script to preprocess the data, perform EDA, and build the classification models.

## Results:

<table>
    <thead>
        <tr>
            <th>Model</th>
            <th>Accuracy</th>
            <th>Precision</th>
            <th>Recall</th>
            <th>F1 Score</th>
            <th>Support</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>XGBoost</td>
            <td>84.67%</td>
            <td>High</td>
            <td>High</td>
            <td>Varies</td>
            <td>Varies</td>
        </tr>
        <tr>
            <td>CatBoost</td>
            <td>87.59%</td>
            <td>High</td>
            <td>High</td>
            <td>Varies</td>
            <td>Varies</td>
        </tr>
        <tr>
            <td>LightGBM</td>
            <td>80.27%</td>
            <td>Good</td>
            <td>Good</td>
            <td>Varies</td>
            <td>Varies</td>
        </tr>
    </tbody>
</table>


## Describing what you will find here: 

1. EDA in EDA.ipynb
2. EDA with machine learning algorithms implementation in EDA_with_algorithms_wothout_smoting.ipynb
3. Machine learning algorithms with SMOTE in ML_with_smoting.ipynb
4. Catboost info in the catboost_info folder.
5. The data folder contains all the data files used.
6. timeline.mov is the video of the project presentation of the project.
