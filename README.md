# Airfoil Self-Noise Regression (Math 10 Final Project)

## 📌 Overview  
This project uses the Airfoil Self-Noise dataset from the Math 10 competition on Kaggle to develop a regression model predicting the *scaled sound pressure* of airfoil panels based on aerodynamic and geometric features.  

##  Dataset  
- **Source**: Math 10 competition on Kaggle  
- **Files**:  
  - `train.csv`: Features + target (`scaled-sound-pressure`)  
  - `test.csv`: Features only  

##  Feature Engineering  
Key engineered features include:  
- `freq_vel_interaction` = frequency × free-stream velocity  
- `strouhal` = (frequency × chord-length) ÷ free-stream velocity  
- Polynomial terms of `strouhal` (squared, cubed)  
- `log_strouhal_angle` = log1p(strouhal × attack-angle)  
- Various interaction terms: attack-angle × velocity, attack-angle × frequency, etc.  

##  Modeling Approach  
- Used a pipeline combining `StandardScaler` and `XGBRegressor`  
- Hyperparameters tuned via `GridSearchCV` with R² scoring and 12-fold CV  
- Best model selected and evaluated on the full training set  

##  Results  
- Best parameters found: `…`  
- Best CV R²: 0.93116  
- Training R²: `0.9401
*(If you have a validation set, add Validation R² here)*  
- Test R² / RMSE: `…`  

##  Submission  
Generated predictions for `test.csv`, packaged into `submission.csv`, ready for upload to Kaggle or use in downstream analysis.  

##  Future Work  
- Incorporate additional physics-based features (e.g., Reynolds number, Mach number)  
- Explore ensemble models and stacking  
- Perform feature importance analysis for interpretability  
- Deploy model as a simple web app or REST API  

##  About  
Achyuta Raghunathan
Math 10 (Introduction to Mathematical Data Science), University of California, Irvine  
06/2/2025
