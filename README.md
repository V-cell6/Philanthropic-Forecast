# 🎯 Sponsor Forecaster

I built a model to predict whether someone earns over $50,000 a year using data from the 1994 U.S. Census. The goal is to help organizations (like charities) identify likely sponsors by estimating income from publicly available features.

## 📋 Data Source

- **Dataset:** [UCI Census Income](https://archive.ics.uci.edu/ml/datasets/Census+Income)  
- **Changes made:**  
  - Dropped `fnlwgt` column  
  - Removed rows with missing or malformed entries
---

##  What I Did

1. **Baseline (Naive Predictor):**  
   - Always predicts “> $50K”  
   - Accuracy = percentage of actual high earners  
   - Recall = 1.0 (catches all true positives)  
   - Precision = low (labels everyone as high earner)  

   This gave a simple benchmark to beat.

2. **Models Tested:**  
   - **Gaussian Naive Bayes**  
     - Fast and simple  
     - Handles many features, but high bias  
   - **Decision Tree**  
     - Easy to interpret  
     - Handles mixed data types, but prone to overfitting  
   - **AdaBoost (Ensemble)**  
     - Combines weak learners into a strong one  
     - Very accurate on clean data, minimal parameter tuning  

3. **Evaluation Metric:**  
   - **F0.5 score** (puts more weight on precision)  
   - Focus on precision because correctly finding high earners is more important than catching every single one

4. **Results:**  
   - **AdaBoost** achieved the best balance of accuracy and F0.5 score across different training sizes (1%, 10%, 100%).  
   - Decision Tree overfit (near-perfect training scores), and GaussianNB lagged behind.  
   - Training time for AdaBoost was higher but prediction time remained fast, which is acceptable for a one-time inference scenario.  

5. **Final Model (Optimized AdaBoost):**  
   - **Accuracy:** 0.8645  
   - **F0.5 Score:** 0.7375  
   - These metrics outperform the naive baseline and the unoptimized model.

---

## Trained Model Performance Metrics Visualisations


![image](https://github.com/user-attachments/assets/c6f3ca77-57b4-4403-87d6-97c46b0c7cf7)



##  Dependencies

```
numpy
pandas
scikit-learn
matplotlib
seaborn
jupyter
```

---

## Key Takeaways

- A naive predictor (always “> $50K”) is a useful baseline but performs poorly in precision.  
- AdaBoost is my top choice: it gives the highest F0.5 score and maintains a fast inference time.  
- Optimizing AdaBoost improves both accuracy and F0.5 score, clearly surpassing the baseline.

---

## Author

**[Your Name]**  
- GitHub: [your-username](https://github.com/your-username)  
- LinkedIn: [your-linkedin](https://www.linkedin.com/in/your-linkedin)  
