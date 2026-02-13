
### Gradient Descent
![[Pasted image 20260213103031.png]]

#### Learning Rate
![[Pasted image 20260213104348.png]]

#### sparce and dense models
- sparce -> many features are equal to zero 
- dense models -> many features are close to zero (but not equal to zero)
![[Pasted image 20260213141435.png]]
#### Regularization
- L1 Regularization (lasso) -> make unimportant features to zero
- L2 Regularization (ridge) -> make unimportant features close to zero
- Combined L1 and L2 Regularization (elastic net) = L1 + L2
- `Lambda is hyperparameter`
![[Pasted image 20260213141018.png]]

### Bias and Variance
- High Bias -> Underfitting (training error)
![[Pasted image 20260213143049.png]]

- High Variance -> Overfitting
![[Pasted image 20260213143332.png]]

![[Pasted image 20260213143522.png]]



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
		![[Pasted image 20260213154420.png]]
