## Mental Disorder Classification Using Random Forest

The dataset I worked with included responses related to conditions like ADHD, PTSD, OCD, anxiety, depression, and others. My goal was to train a model that could recognize the underlying patterns in the data and accurately classify each disorder.

---

### Dataset

I used a dataset called `Mental disorder symptoms.xlsx` (private/unpublished). Before feeding it into the model, I spent time cleaning and preparing it. This included:
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

While the results were encouraging, the model wasn’t perfect. I noticed that it often confused two specific disorders: Major Depressive Disorder (MDD) and Persistent Depressive Disorder (PDD). Each was misclassified as the other once.

This made sense when I looked closer — the sample size for both was extremely small (only two samples each), and their symptom patterns overlapped a lot. That explained why the model had a harder time telling them apart.

---

### Visual Insights

To better understand the model’s behavior, I visualized:
- Feature importance — to see which symptoms were most influential in making predictions
- A confusion matrix — to pinpoint exactly where misclassifications occurred (confirming that errors only happened between MDD and PDD)


### Reflections

Working on this project was not just technically rewarding, but also meaningful. Mental health is deeply personal and complex. While this model isn’t a diagnostic tool, I believe projects like this can help us understand patterns better, support early detection efforts, and inspire more conversation around mental health in tech and data science spaces.

If you're curious, feel free to go through the notebook and reach out — I’d love to hear your thoughts.
