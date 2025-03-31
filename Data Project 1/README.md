# StackOverflow Developer Survey 2024 -- Data Analysis

**Data Download:**
The data can be downloaded from <https://survey.stackoverflow.co/2024/> (Currently data is not added to repository due to large size).

**Business Understanding:**
The annual Stack Overflow Developer Survey provides insights into developer work environments, compensation, technology usage, and job satisfaction. The analysis in this notebook aims to identify key factors influencing developer job satisfaction in the 2024 dataset, offering actionable insights for companies and professionals.

**Key Questions:**
* How much does compensation impact job satisfaction?
* Does remote work influence job satisfaction?
* What other factors play a significant role?

**Data Understanding:**
The 2024 dataset consists of responses to 113 survey questions from 65,437 developers worldwide. However, many responses were voluntary, leading to a high proportion of missing data. The target variable, job satisfaction, is measured on a 0-10 scale, with 29,126 responses available.

**Data Preparation**
Since most responses are in textual format, they require transformation into numerical features for analysis. Survey responses are categorized into multi-choice and single-choice questions, with the latter further classified as ordinal or categorical. Due to extensive missing data and individual variability, only sufficiently populated features are retained, and rows with missing values in key variables are removed.

**Data Cleaning Steps:**
* Multi-choice responses: Converted into numerical counts of selected items.
* Single-choice responses: Encoded as ordinal or one-hot variables.
* Numerical responses: Standardized for comparability (e.g., currency values adjusted across countries).
* Missing data: Features with excessive missing values are excluded; remaining missing values are handled by row-wise deletion.

**Modeling:**
A Random Forest Regressor is trained to predict job satisfaction based on the processed features. GridSearchCV was leveraged for hyperparameter tuning.

**Evaluation:**
Model performance is assessed using Mean Squared Error (MSE). To interpret feature importance, both Random Forest feature rankings and SHAP values are analyzed.

**Insights Sharing:**
Key findings and insights are shared in the following Medium blog post: [What Drives Developer Job Satisfaction? Insights from the Stack Overflow 2024 Survey](https://medium.com/@jana.backhus/what-drives-developer-job-satisfaction-insights-from-the-stack-overflow-2024-survey-5d8ddaa34e7e)
