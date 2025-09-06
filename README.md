## Mental Disorder Classification Using Random Forest

The dataset I worked with included responses related to conditions like ADHD, PTSD, OCD, anxiety, depression, and others. My goal was to train a model that could recognize the underlying patterns in the data and accurately classify each disorder.

---

### Dataset

I used a dataset called `Mental disorder symptoms.xlsx`. Before feeding it into the model, I spent time cleaning and preparing it. This included:
- Removing missing values to ensure consistency
- Dropping duplicates to avoid data bias
- Separating the features from the target labels (the disorder type)
- Performing a stratified train-test split so that each disorder was fairly represented

---

### Model Development

I chose a Random Forest classifier because of its simplicity and effectiveness for classification tasks involving multiple classes. I trained the model using 100 estimators and fixed the random state to keep results reproducible.

After training, I evaluated the model's performance. Here’s what I found:
- Test Accuracy: 91%
- Cross-Validation Accuracy (5-fold): 93%

Most disorders were predicted correctly across the board. Out of 12 total disorders, 10 were classified with perfect precision, recall, and F1-score.

---

### What I Discovered

I noticed that it often confused two specific disorders: Major Depressive Disorder (MDD) and Persistent Depressive Disorder (PDD). Each was misclassified as the other once.

This made sense when I looked closer — the sample size for both was extremely small (only two samples each), and their symptom patterns overlapped a lot. That explained why the model had a harder time telling them apart.

---

### Improved Model: XGBoost with SMOTE + Hyperparameter Tuning

To overcome class imbalance, I applied **SMOTE** and then trained an **XGBoost classifier** with hyperparameter tuning.  

### Performance
- **Test Accuracy:** 95%  
- **Cross-Validation Accuracy (5-fold):** 96%  
This significantly reduced misclassifications between **Major Depressive Disorder (MDD)** and **Persistent Depressive Disorder (PDD).
  
---


### Key Insights

**Important Predictors (from Feature Importance + SHAP):**
- Hallucinations  
- Change in eating patterns  
- Hopelessness  
- Nightmares  
- Sweating  
- Close friend (support factor)  
- Increased energy  
- Introversion  
- Avoidance of activities  
- Concentration difficulties  

These features consistently emerged as the most influential in determining mental health disorder classification.  

---


### Reflections

Working on this project was not just technically rewarding, but also meaningful. Mental health is deeply personal and complex. While this model isn’t a diagnostic tool, I believe projects like this can help us understand patterns better, support early detection efforts, and inspire more conversation around mental health in tech and data science spaces.


