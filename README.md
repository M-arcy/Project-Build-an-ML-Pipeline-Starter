# **Building an End-to-End ML Pipeline for Short-Term Rental Prices in NYC**

This project demonstrates how to build an **end-to-end machine learning (ML) pipeline** to predict short-term rental prices in New York City (NYC). The pipeline automates all necessary steps, from data ingestion and cleaning to training and testing, using tools like **MLflow**, **Weights & Biases (W&B)**, and **Hydra** for seamless configuration, tracking, and reproducibility.

The project is designed for a property management company that rents rooms and properties for short periods. Given the continuous inflow of new property data, the pipeline must retrain the model regularly to remain accurate and relevant.

---

## **Project Overview**

- **Goal:** Build a reusable pipeline that estimates rental prices based on data for similar properties.
- **Tools:**  
  - **MLflow**: Tracks experiments and orchestrates the pipeline steps.
  - **Weights & Biases (W&B)**: Monitors, visualizes, and version-controls datasets and models.
  - **Hydra**: Manages configuration files for flexible parameter tuning.
  - **GitHub**: Stores code and version-controlled components.
  
The pipeline stages include:
1. **Data ingestion and cleaning**
2. **Exploratory data analysis (EDA)**
3. **Train-test split creation**
4. **Model training and evaluation**
5. **Hyperparameter optimization**
6. **Test set verification**
7. **Pipeline release for production**

---

## **1. Prerequisites**

Before beginning, ensure that you have the following:

- **Operating System:** Ubuntu (22.04 or 24.04), macOS (recent versions), or Windows using WSL2.
- **Python Version:** Python 3.10 or higher.
- A GitHub account for version control and project hosting.
- An account on **Weights & Biases (W&B)** for experiment tracking and artifact storage.

---

## **2. Environment Setup**

The required environment is created using **conda** and the provided configuration files. This includes all necessary dependencies such as MLflow, W&B, and Hydra. Once the environment is set up, activate it to run the pipeline.

---

## **3. Weights & Biases (W&B) Login**

**Weights & Biases** (W&B) is used to log experiment runs, track metrics, and store artifacts. Ensure you log into W&B using your personal API key, which can be obtained from the W&B dashboard. Logging in connects the pipeline to your W&B workspace and enables seamless tracking of pipeline steps and outputs.

---

## **4. Configuration Management**

This project uses **Hydra** for configuration management. All parameters controlling the pipeline, such as dataset paths, model settings, and hyperparameters, are specified in the `config.yaml` file. 

Key configuration sections include:
- **Main:** Contains general settings like project name and steps to run.
- **ETL:** Controls data extraction and cleaning parameters (e.g., min/max price thresholds).
- **Modeling:** Specifies parameters for the machine learning model (e.g., number of estimators, maximum depth).
  
No parameters should be hardcoded within the scripts. Instead, reference values from the configuration file for flexibility and reusability.

---

## **5. Running the Pipeline**

The ML pipeline is executed using MLflow, either as a full end-to-end run or by selecting specific steps. You can customize the run by specifying which parts of the pipeline to execute, such as downloading the data, performing data cleaning, or training the model. 

In addition to selecting steps, parameters can be overridden directly in the run command to quickly test different configurations without modifying the `config.yaml` file.

---

## **6. Pipeline Components**

This project simulates a real-world scenario by including reusable components hosted in a GitHub repository. These pre-built components perform key tasks such as:
- **Data Download:** Fetches the raw dataset.
- **Data Splitting:** Splits the cleaned dataset into training, validation, and testing sets.
- **Model Training:** Trains a **Random Forest Regressor** model using the preprocessed data.
- **Model Testing:** Evaluates the model's performance on the test dataset and logs metrics such as Mean Absolute Error (MAE).

The components are linked via MLflow, and their settings are configured in the `config.yaml` file. Each component is designed to be reusable in other projects.

---

## **7. Error Handling and Troubleshooting**

Common issues may include:
- **Corrupted Conda Environments:** If an environment becomes corrupted, it may need to be removed and recreated.
- **Version Conflicts:** Ensure that all dependencies, including Python, MLflow, and W&B, are consistent across the pipeline steps to avoid runtime errors.
- **Connection Issues:** Confirm that you are logged into W&B and have a stable internet connection when running the pipeline to ensure artifact uploads and logging work as expected.

Error logs and status updates are automatically tracked in W&B, providing insights into any failures during the pipeline run.

---

## **License**

This project is distributed under the terms outlined in the `LICENSE.txt` file.
