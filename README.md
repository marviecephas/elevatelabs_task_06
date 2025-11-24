# Task 6: K-Nearest Neighbors (KNN) Classification (Iris Dataset)

### Objective
The primary goal was to implement the K-Nearest Neighbors (KNN) algorithm for multi-class classification, focusing on the essential preprocessing step (Normalization) and validating the model by finding the optimal hyperparameter $K$.

### Dataset & Preprocessing
* **Dataset:** Iris Dataset (Multi-class classification with three output classes).
* **Encoding:** The categorical target variable ('Species') was converted using **Label Encoding**.
* **Feature Scaling (Mandatory):** All predictor features were scaled using **MinMaxScaler (Normalization)** to a range of $[0, 1]$. This step is **critical** for KNN because it relies on the Euclidean distance metric. Unscaled features with larger magnitudes would unfairly bias the distance calculation.

---

### Methodology: Finding the Optimal K

The value of $K$ (the number of neighbors) directly controls the bias-variance trade-off in the KNN model. 

[Image of K-Nearest Neighbors classification]


1.  **K-Value Experimentation:** An iterative approach was implemented, training and testing the KNN model for a range of $K$ values (from $K=1$ to $K=25$) to identify the setting that yields the best performance.
2.  **Optimal Selection:** The $K$ value that yielded the highest mean accuracy on the test set was selected as the final hyperparameter. 

#### **Optimal K Results**
* **Optimal K Found:** **1**
* **Best Testing Accuracy:** **0.9333**

---

### Model Evaluation

The final model was trained using the optimal $K$ and evaluated on the test set.

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Final Accuracy** | **0.9333** | The model's overall prediction correctness on unseen data. |
| **Precision (Weighted Avg.)** | **0.94** | Measures the model's confidence in its positive predictions across all three classes. |
| **Recall (Weighted Avg.)** | **0.93** | Measures the model's ability to identify all actual positive cases across all three classes. |

#### **Conceptual Insights**

* **Distance Metric:** The model uses **Euclidean Distance** (L2 norm) to determine neighborhood proximity, validating the need for the prior normalization step.
* **Time Complexity:** KNN is a **lazy learning** algorithm; it performs no training during the `fit()` phase. Its high computational cost occurs during the prediction phase, where it must calculate the distance to every single training point.
