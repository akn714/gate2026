
### Gradient Descent
<img src="./BIN/Pasted image 20260213103031.png">

#### Learning Rate
<img src="./BIN/Pasted image 20260213104348.png">

#### sparce and dense models
- sparce -> many features are equal to zero 
- dense models -> many features are close to zero (but not equal to zero)
<img src="./BIN/Pasted image 20260213141435.png">
#### Regularization
- L1 Regularization (lasso) -> make unimportant features to zero
- L2 Regularization (ridge) -> make unimportant features close to zero
- Combined L1 and L2 Regularization (elastic net) = L1 + L2
- `Lambda is hyperparameter`
<img src="./BIN/Pasted image 20260213141018.png">

### Bias and Variance
- High Bias -> Underfitting (training error)
<img src="./BIN/Pasted image 20260213143049.png">

- High Variance -> Overfitting
<img src="./BIN/Pasted image 20260213143332.png">

<img src="./BIN/Pasted image 20260213143522.png">



#### Tradeoff (balance between bias and variance)
- The bias-variance tradeoff suggests that there is a balance to be struck between bias and variance. As you decrease bias (by increasing model complexity), you typically increase, and vice verse.
- The goal is to find the right level of model complexity that minimizes the combined error  due to bias and variance. The objective is to achieve a model that generalizes well to new,  unseen data.


## Techniques
- Regression
	- Linear Regression
	- Polynomial Regression
- Classification
	- KNN (k is chosen odd, k is hyperparameter)
		- large k -> underfitting (high bias)
		- small k -> overfitting (high variance & low bias)
	- Logistic Regression
		- Predicts the probability that an input belongs to a specific class
		- Binary classification -> 0/1, True/False, Yes/No
		- Users sigmoid function
		<img src="./BIN/Pasted image 20260213154420.png">

#### Naive Bayes
**Marginal Probability**
<img src="./BIN/Pasted image 20260215001353.png">
### SVM (Support Vector Machine)
- It is a supervised machine learning algorithm
- Used for classification and regression both
- hyper plane: `w.x + b = 0`
- **Support Vectors**: nearest points to the plant `w.x + b = 0`
- **Kernel function**: It transforms data into a higher-dimensional space to make it linearly separable.
- **Types of kernels**:
	- Linear kernel: suitable for linearly separable data.
	- Polynomial kernel: for curved boundaries.
	- Radial Basis Function (RBF) kernel: captures complex relationships.
- **Hard margin linear svm**: it has 100% accuracy.
- Equation of hyper plane: alpha(i): parameters, S(i): support vectors
<img src="./BIN/Pasted image 20260214190009.png">
<img src="./BIN/Pasted image 20260214235026.png">
<img src="./BIN/Pasted image 20260214185136.png">

### Bottom Up clustering
<img src="./BIN/Pasted image 20260214225317.png">

### Distance Measures
<img src="./BIN/Pasted image 20260214225439.png">

### Measure of dissimilarity
- Single Linkage - take minimum distance between both groups data points
- Complete Linkage - take maximum distance between both groups data points
- Average Linkage - take average of all the distance between both groups data points
<img src="./BIN/Pasted image 20260214225937.png">
<img src="./BIN/Pasted image 20260214230342.png">


### Dimensionality Reduction
- Principal Component Analysis (PCA)
- Linear Discriminant Analysis (LDA)
- Kernel PCA
- Quadratic Discriminant Analysis (QDA)
#### Linear Discriminant Analysis
- Supervised ML algorithm
- Used for classification tasks
- Uses Dimensionality Reduction
- **Definition**: The goal is to find linear combination of features that maximizes the separation between different classes while minimizing the spread (variance) within each class.
	- Maximizing Mean Difference
	- Minimizing Within-Class Scatter
<img src="./BIN/Pasted image 20260214191525.png">
<img src="./BIN/Pasted image 20260214212738.png">


---

## PYQs

**Naive Bayes Classifier**
<img src="./BIN/Pasted image 20260214170033.png">

**Parameter Estimation in naive bayes classifier**
<img src="./BIN/Pasted image 20260214182058.png">

**Naive Bayes** (misclassifying)
<img src="./BIN/Pasted image 20260214233246.png">

