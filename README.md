# Performance-Prediction-in-F1

Overview:
This project aims to predict two key aspects of Formula 1 races:

  1. Striking Distance Prediction - Using lap data to predict the likelihood of a chaser catching up to the leader.

  2. Overtake Likelihood Prediction - Using telemetry data to evaluate if a chaser can successfully overtake the leader.

The project uses pre-extracted race data for training and testing to overcome the limitations of API rate limits during live predictions.


Dataset Description:

We have four main CSV files which contain the necessary data for training and testing our machine learning models:

  1. train_laps.csv - This dataset includes lap-by-lap information for the years 2022-2024, which is used for training the Striking Distance Prediction model.

  2. test_laps.csv - This dataset holds lap data specifically for the year 2025, which is used for testing the Striking Distance Prediction model.

  3. telemetry_features.csv - This dataset contains telemetry data (such as speed, throttle, and brake averages) collected for each driver pair from 2022-2024, used for training the Overtake Likelihood Prediction model.

  4. test_telemetry_features.csv - This is the testing set for telemetry data, specifically for the year 2025.

Setup Instructions:

To successfully run the Performance_Prediction_in_F1.ipynb notebook, please follow the steps below:

  1. Environment Setup:
     Ensure you have the Python libraries installed from requirement.txt

  2. Folder Structure:

    Place the following CSV files in the root directory: If this does not work for you then directly edit the path of stored csv files in "save_path" variable

    Copy
    Edit
    ├── Performance_Prediction_in_F1.ipynb
    ├── train_laps.csv
    ├── test_laps.csv
    ├── telemetry_features.csv
    └── test_telemetry_features.csv

  3. API Limitations and Data Caching:
     - The FastF1 API, which is used to fetch telemetry and lap data, has a limit of 500 requests/hour.
     - To overcome this limitation and speed up the workflow, I have pre-fetched all required data for 2022-2024 (for training) and 2025 (for testing) and stored them in the respective CSV files.
     - This allows the notebook to load data directly from the CSVs instead of making repeated API calls, ensuring faster execution and bypassing API rate limits.
       
  5. Open the Jupyter Notebook: Performance_Prediction_in_F1.ipynb

     Run each cell sequentially:

     The notebook will:
       - Load datasets from CSV files.( Do not run any cells which is fetching data from FastF1 API, it will take lot of time to set up the dataset. Hence, I have saved the required data in csv files).
       - Perform preprocessing and feature engineering.
       - Train models for both Striking Distance and Overtake Likelihood.
       - Evaluate models and display performance metrics.
     
  7.   Model Outputs:

       At the end of the notebook, you will find:
        - Performance reports for both prediction tasks.
        - SHAP analysis for interpretability.
        - Graphical representations of model predictions.
  
