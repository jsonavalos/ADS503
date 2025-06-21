# ADS503 

names: "Jason Avalos, Lindy Conrad, Duy-Anh Dang"

---

### Table of Contents

- [Description](#description)
- [Setup&Reproducibility](#Setup&Reproducibility)
- [Deployment Process](#deployment)
- [Monitoring](#monitoring)
- [Technologies](#technologies)
- [License](#license)

---

## Description

### Summary of the Project

This project aims to classify small molecules as potential inhibitors of the Sirtuin6 protein based on six chemical descriptors. The dataset includes 100 molecules labeled with "High_BFE" or "Low_BFE" classes. We use various supervised learning models to evaluate their predictive performance using ROC-AUC as the key metric.

The overall pipeline includes exploratory data analysis, data preprocessing (normalization), model training (with hyperparameter tuning), evaluation using cross-validation, and selection of the best-performing model.

### Data Sources and Preparation

To ensure reproducibility:

- All relevant libraries are loaded at the beginning using a setup chunk.
- A fixed seed (`set.seed(123)`) is used across modeling steps to ensure consistent results.
- Preprocessing includes centering and scaling of predictors using the `caret::preProcess()` function.
- Data is split into 80% training and 20% testing using `caret::createDataPartition()`.


# Setup & Reproducibility 

**Required Libraries:**

library(tidyverse)
library(caret)
library(pROC)
library(randomForest)
library(e1071)
library(glmnet)
library(corrplot)

This project is designed to be fully reproducible from the GitHub repository. Follow these steps to set up the pipeline locally:

## clone Repository

git clone https://github.com/jsonavalos/ADS503/tree/main


### Future Enhancements

To potentially further improve and extend this project:

- Increase Dataset Size: Acquire more labeled molecules to boost model generalizability and reduce variance.

- Feature Engineering: Explore domain-specific chemical transformations and interaction terms to enhance signal.

- Advanced Models: Implement XGBoost or neural networks for potentially improved accuracy.

- Ensemble Methods: Combine top-performing models using stacking or voting for robust prediction.

- Automated ML Pipelines: Integrate mlr3 or tidymodels for scalable, reproducible workflows.

- Deployment: Package the final model in a Shiny dashboard or REST API for user-friendly predictions.




---

# Monitoring

While this is a one-time batch project, monitoring of model performance is simulated using:

- Cross-validation performance summaries (mean/SD of AUC)

- ROC analysis on test set to verify generalization

- Confidence intervals for model AUCs to detect statistical significance

If deployed in production, additional monitoring tools (e.g., model drift, performance on new data) would be required.


### Security and Ethical Considerations

Data Sensitivity: The dataset does not contain personally identifiable information (PII), reducing privacy risks.

Bias and Fairness: The model assumes no inherent bias in class labeling. If new data sources are introduced, fairness audits should be conducted.

Model Interpretability: Logistic regression and Lasso are interpretable models; however, ensemble methods (e.g., Random Forest) may require SHAP or LIME explanations.

Intended Use: The model is for academic exploration. Any real-world pharmacological applications must involve clinical validation and regulatory review.

Security: If hosted, secure access to model endpoints and protect against adversarial inputs or model inversion attacks.


#### Technologies

- R (RStudio IDE): Main environment for data analysis and modeling

- caret: Model training, validation, preprocessing

- pROC: ROC curve analysis and AUC computation

- randomForest, e1071, glmnet: Model implementations for ensemble, SVM, and regularized regression

- ggplot2: Visualization for EDA and diagnostics

- corrplot: Visualizing correlation matrices


[Back To The Top](#ADS503)

---

## License

MIT License


Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[Back To The Top](#ADS503)




