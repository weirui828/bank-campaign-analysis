# Bank Marketing Campaign Analysis

This project uses multiple machine learning classifiers to analyze the efficiency of telemarketing campaigns for a Portuguese banking institution. Our primary goal is to predict whether a client will subscribe to a bank term deposit based on a variety of features, including client demographics, last contact details, and macro-economic indicators.

## Jupyter Notebook
The complete analysis, including exploratory data analysis, data preparation, modeling, hyperparameter tuning, and evaluation, can be found here: 
[campaign_analyzer.ipynb](campaign_analyzer.ipynb)

## Summary of Findings

1. **Performance Context**:
   The dataset is highly imbalanced, with roughly 89% of customers declining the term deposit. Therefore, standard "Accuracy" is not a reliable metric. We evaluated our models based on ROC-AUC, which gauges the model's ability to rank true subscribers higher than non-subscribers.

2. **Model Comparisons**:
   After testing Logistic Regression, K-Nearest Neighbors (KNN), Decision Trees, and Support Vector Machines (SVM), we found that the **Tuned Logistic Regression** and **Tuned SVM** models yielded the best performance (with a ROC-AUC score of approximately 0.79-0.80). Logistic Regression is particularly advantageous as it is both computationally efficient and highly interpretable.

3. **Key Drivers**:
   * **Macroeconomic Indicators**: Variables such as the employment variation rate (`emp.var.rate`) and Euribor 3-month rate (`euribor3m`) strongly influence the outcome. Poor economic conditions or high employment variation correlate with clients avoiding term deposits.
   * **Prior Engagement**: The `pdays` feature (days since the client was last contacted) is highly significant. Clients who had a recent and successful prior contact are substantially more likely to subscribe. 
   * **Timing**: The month of the contact heavily influenced the success rate. For example, contacts made in May saw a large volume of rejections.

## Actionable Recommendations
- **Target "Warm" Leads**: Clients who have been contacted in previous campaigns and had a successful interaction should be prioritized.
- **Timing and Economic Context**: Marketing efforts should be scaled based on the broader economic environment. During times of low consumer confidence or high employment variation, aggressive campaigns may yield lower returns.
- **Resource Optimization**: Using our Tuned Logistic Regression model, the bank can score potential clients. Call center agents should direct their focus strictly toward clients who score in the highest percentiles of predicted probability, drastically reducing time and money wasted on unlikely prospects.
