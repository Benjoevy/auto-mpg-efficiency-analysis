# Auto MPG Efficiency Predictor 🚗

An end-to-end Machine Learning regression project focused on predicting vehicle fuel efficiency (MPG) using physical attributes and technical specifications.

## 📌 Project Overview
This project demonstrates a full data science workflow, from raw data ingestion to model interpretation. The goal is to build a reliable model that predicts a car's Miles Per Gallon (MPG) while identifying the most significant factors that contribute to fuel consumption.

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn

## 📊 Methodology

### 1. Data Preprocessing & Cleaning
I implemented a robust cleaning pipeline to ensure data quality and model stability:
* **Handling Non-Numeric Data:** Converted the `horsepower` column to numeric, using coercion to handle irregular characters like `?`.
* **Imputation:** Missing horsepower values were filled using the **median**, ensuring outliers did not skew the data.
* **Target Integrity:** Removed rows with missing `mpg` values and completely empty records to maintain a clean training set.
* **Re-indexing:** Reset the data index after cleaning to ensure a continuous sequence for processing.

### 2. Feature Engineering
* **Categorical Encoding:** Applied **One-Hot Encoding** to the `origin` feature using `pd.get_dummies` with `drop_first=True` to avoid the dummy variable trap.
* **Feature Selection:** Dropped the `car_name` column to prevent the model from overfitting on unique row identifiers.
* **X/Y Separation:** Defined the feature matrix ($X$) and the target vector ($y$) for the regression task.

### 3. Model Pipeline
* **Train-Test Split:** Used an **80/20 split** with a fixed `random_state=42` to ensure experimental reproducibility.
* **Feature Scaling:** Implemented `StandardScaler` to normalize the data, ensuring features like weight (thousands) and cylinders (single digits) are treated with equal importance by the model.
* **Algorithm:** Trained a **Linear Regression** model to establish a clear, interpretable relationship between features and MPG.

## 📈 Evaluation & Results
The model was evaluated using standard regression metrics to verify generalization:

* **R-Squared ($R^2$):** Quantifies how much variance in MPG is explained by the model.
* **RMSE & MAE:** Measured the average error in actual Miles Per Gallon units to understand prediction accuracy.
* **Feature Importance:** Extracted model coefficients to visualize which attributes (like weight or year) have the highest impact on fuel efficiency.

## 🏁 Conclusion
The project successfully highlights that while physical mass (weight) is the primary predictor of fuel consumption, there is a clear positive trend in efficiency as `model_year` increases. This suggests that engineering advancements have consistently improved MPG over time, independent of vehicle size.

## 📬 Contact
**Benjamin Ilevbare** 
* **LinkedIn:** [linkedin.com/in/benjoevy](https://linkedin.com/in/benjoevy)
* **Email:** ilevbarebenjaminjoseph@gmail.com

---
*If you found this project helpful, feel free to ⭐ the repository!*

## 🚀 How to Use
1. Clone the repo: `git clone https://github.com/benjoevy/auto-mpg-efficiency-analysis.git`
2. Install dependencies: `pip install pandas scikit-learn seaborn`

3. Open `auto_mpg_project.ipynb` in Jupyter Notebook or VS Code.


