# 🚀 **K-Nearest Neighbors (KNN) Classifier: Predicting Purchase Decisions** 📊

Welcome to my K-Nearest Neighbors (KNN) Classifier project! 🚀

This project demonstrates how we can use KNN to predict whether a user will purchase a product based on their age and estimated salary. The dataset comes from a social network ad campaign.

## 📺️ Project Overview

- **Dataset:** Social Network Ads
- **Algorithm:** K-Nearest Neighbors (KNN)
- **Key Techniques:** Feature scaling, train-test split, and model evaluation.

## ⚙️ Workflow

1. **Data Importing:** We begin by loading the dataset using pandas.
2. **Data Preprocessing:**
   - Splitting into training and test sets.
   - Applying feature scaling to normalize the data.
3. **Model Training:** KNN classifier with Minkowski distance (p=2).
4. **Prediction & Evaluation:**
   - Generating predictions on the test set.
   - Using a confusion matrix and accuracy score to evaluate performance.
5. **Visualization:**
   - Plotting decision boundaries for both training and test sets.

## 🌛 Why Feature Scaling Matters?

Feature scaling ensures that all the features contribute equally to the distance calculations. In our dataset, `Age` ranges from a few years to decades, while `Estimated Salary` varies significantly. Without scaling, `Salary` would dominate the distance computations, leading to biased predictions.

We use **StandardScaler** to standardize the features, giving them a mean of 0 and a standard deviation of 1.
- ![alt text](https://github.com/tanveerj5/K-Nearest-Neighbors-KNN-Classifier-Predicting-Purchase-Decisions/blob/main/train%20resolution%20with%20feature-scaling.png)
- ![alt text](https://github.com/tanveerj5/K-Nearest-Neighbors-KNN-Classifier-Predicting-Purchase-Decisions/blob/main/test%20resolution%20with%20feature-scaling.png)
- ![alt text](https://github.com/tanveerj5/K-Nearest-Neighbors-KNN-Classifier-Predicting-Purchase-Decisions/blob/main/output%20with%20feature-scaling.png)

### ⚠️ Why Won't KNN Work Without Feature Scaling?

KNN calculates distances between data points to make predictions. If we don't scale the features:

- Features with larger ranges (like `Estimated Salary`) will overshadow those with smaller ranges (like `Age`).
- Distance calculations become skewed, affecting the classification boundaries.
- The model may perform poorly, especially when features are measured in different units.
  
- ![alt text](https://github.com/tanveerj5/K-Nearest-Neighbors-KNN-Classifier-Predicting-Purchase-Decisions/blob/main/train%20resolution%20without%20feature-scaling.png)
- ![alt text](https://github.com/tanveerj5/K-Nearest-Neighbors-KNN-Classifier-Predicting-Purchase-Decisions/blob/main/test%20resolution%20without%20feature-scaling.png)
- ![alt text](https://github.com/tanveerj5/K-Nearest-Neighbors-KNN-Classifier-Predicting-Purchase-Decisions/blob/main/output%20without%20feature-scaling.png)

For example:
- Age typically ranges from 20 to 60, while Salary can range from 20,000 to 200,000.
- Without scaling, salary differences dominate the distance, making age irrelevant in predictions.

## 📊 Why Minkowski Distance with p=2?

In KNN, the distance between points is crucial. We use the Minkowski distance with `p=2`, which effectively calculates the **Euclidean distance**.

- **Minkowski Distance Formula:**

  $$d(x, y) = \left(\sum_{i=1}^{n} |x_i - y_i|^p\right)^{\frac{1}{p}}$$

- For `p=2`, it becomes the **Euclidean distance**:

  $$d(x, y) = \sqrt{\sum_{i=1}^{n} (x_i - y_i)^2}$$

Euclidean distance is intuitive and works well when features are scaled, making it ideal for our dataset.

### ❌ Why Not Manhattan Distance?

The Manhattan distance (Minkowski with p=1) calculates distances along axes, which might not capture the actual spatial relationship as effectively as Euclidean distance when features are scaled. Euclidean distance considers the shortest path, which aligns better with our data structure.

## 📊 Model Performance

- **Confusion Matrix**: Showcases how many predictions were correct and where the model made mistakes.
- **Accuracy Score**: Measures overall performance.
- 
The decision boundaries for the training and test sets visually represent how well the model separates the two classes.

## 🚀 Key Takeaways

- Feature scaling is essential when features have different ranges.
- KNN won't work effectively without scaling when features differ significantly in magnitude.
- Euclidean distance (Minkowski with p=2) is intuitive and effective for spatial data.
- KNN is simple yet powerful when paired with proper preprocessing.
- Manhattan distance is less effective for this dataset.

Thanks for exploring my KNN project! 😊🔍
