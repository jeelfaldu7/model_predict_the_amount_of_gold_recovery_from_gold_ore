# 🏆 Gold Recovery Prediction using Machine Learning
Zyfra, a company focused on efficiency solutions for heavy industries, developed a machine learning prototype. The goal is to build a machine learning model that predicts the amount of gold recovered from ore at various stages of the extraction and purification process. This model helps optimize production, reduce losses, and eliminate unprofitable parameters in the gold mining workflow. 

## 🎯 Project Objective
  - Develop a model to predict two critical targets:
      - `rougher.output.recovery`: Rougher gold concentrate recovery
      - `final.output.recovery`: Final gold concentrate recovery

## 📊 Project Description
  -  The project explores industrial process data related to gold extraction and purification. A regression model was developed to predict gold recovery efficiency using training data and tested on a test set.
  -  The solution includes:
     - Data validation and feature alignment (handling missing columns between train and test)
     - Metal concentration trends across purification stages
     - Abnormality detection (e.g., total concentration = 0)
     - Model evaluation using the Symmetric Mean Absolute Percentage Error (sMAPE) metric
     - Final model tested on real-world-like data simulating future operational input.

## 📄 Table of Contents
  - Project Description
  - Dataset Description
  - Model Training & Testing
  - Results
  - Tools and Libraries
  - How to Run the Project
  - Credits

## 📁 Dataset Description
  - Three datasets were used:
      - `gold_recovery_train.csv`: Contains training data with features and targets.
      - `gold_recovery_test.csv`: Contains features only (targets hidden).
      - `gold_recovery_full.csv`: Source data for analysis.
  - All datasets are time-indexed, and features near each other temporally are often correlated.

## 🧠 Model Training & Testing
  - Two regression models were evaluated:
      - Decision Tree Regressor
      - Random Forest Regressor (with GridSearchCV for tuning)
  - To evaluate performance, sMAPE was calculated for:
      - Rougher process
      - Final recovery stage
      - Combined weighted sMAPE as final metric

## 📈 Results
| Model                           | Rougher sMAPE | Final sMAPE | Combined Final sMAPE |
| ------------------------------- | ------------- | ----------- | -------------------- |
| Decision Tree Regressor (Train) | 9.28          | 8.41        | 8.63                 |
| Random Forest Regressor (Train) | 7.68          | 5.90        | 6.37                 |
| Decision Tree Regressor (Test)  | 9.20          | 10.20       | 10.00                |

Despite Random Forest yielding better accuracy, Decision Tree was chosen for test predictions due to its faster execution time, especially when working under limited computational resources.

## ⚙️ Tools and Libraries
- Python
- Pandas
- Numpy
- Sklearn
- Matplotlib
- Seaborn
- Jupyter Notebook
- GitHub for version control

## 🛠 How to Run the Project:
  1. Clone this repo
     ```bash
     git clone https://github.com/your-username/gold-recovery-prediction.git
     cd gold-recovery-prediction
  2. Create virtual environment
     ```bash
     python -m venv venv
     source venv/bin/activate  # On Windows use `venv\Scripts\activate`
  3. Install dependencies
     ```bash
     pip install -r requirements.txt

## 🤝 Credits
This project was created as part of the TripleTen Data Science program. Special thanks to: 
  - TripleTen instructors and peers for ongoing support and feedback

## 🛡️ License
This project is licensed under the MIT License.
