# BreastCancerDetection

The breast cancer dataset is a classic and very easy binary classification dataset. It contains features computed from a digitized image of a fine needle aspirate (FNA) of a breast mass and describe characteristics of the cell nuclei present in the image.

Link to Dataset: https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html

In our dataset we have the outcome variable or Dependent variable i.e Y having only two set of values, either M (Malign) or B(Benign). So we will use Classification algorithm of supervised learning.

The following are the list of algorithms we use:
- Logistic Regression
- Nearest Neighbor
- Support Vector Machines
- Naïve Bayes
- Decision Tree Algorithm
- Random Forest Classification

## Results ##

<img width="716" alt="Screenshot 2022-12-29 at 14 28 45" src="https://user-images.githubusercontent.com/82876331/209907276-6ffe1e20-c328-4e86-b15f-757a59f0d1ed.png">

<img width="716" alt="Screenshot 2022-12-29 at 14 28 53" src="https://user-images.githubusercontent.com/82876331/209907282-62e962f7-5291-4c9b-ade8-13747a91d96f.png">

<img width="716" alt="Screenshot 2022-12-29 at 14 28 56" src="https://user-images.githubusercontent.com/82876331/209907291-6829e328-8a0b-4eae-8d9d-a8f943fec536.png">

### Final Results ###

<img width="561" alt="Screenshot 2022-12-29 at 14 29 41" src="https://user-images.githubusercontent.com/82876331/209907340-55fb8ccc-68ae-47b5-8c61-254881ac3f56.png">

## Hyperparameter Tuning ##

We use GridSearchCV to improve the results that we previously got.
For Logistic Regression we used the following parameters:
- max_iter= 1000
- solvers = ['lbfgs', 'liblinear', 'newton-cg', 'newton-cholesky', 'sag', 'saga']
- penalty = ['l2', 'l1', 'elasticnet']
- c_values = [1000, 100, 10, 1.0, 0.1, 0.01, 0.001]
= Best: 0.990635 using {'C': 10, 'penalty': 'l1', 'solver': 'saga'}

For Nearest Neighbour:
- n_neighbors = range(1, 21, 2)
- weights = ['uniform', 'distance']
- metric = ['euclidean', 'manhattan', 'minkowski']
= Best: 0.982023 using {'C': 10, 'gamma': 0.01, 'kernel': 'rbf'}

For Support Vector Machines:
- kernel = ['poly', 'rbf', 'sigmoid']
- C = [1000, 100, 10, 1.0, 0.1, 0.01, 0.001]
- gamma = [0.02, 0.01]
= Best: 0.982023 using {'C': 10, 'gamma': 0.01, 'kernel': 'rbf'}

For Naive Bayes:
We don't have any parameters

For Decision Tree Classifier:
- criterion = ['gini', 'entropy', 'log_loss']
- max_depth = [4,5,6,7,8,9,10,11,12,15,20,30,40,50,70,90,120,150]
- max_leaf_nodes = [2,4,6,10,15,30,40,50,100]
- min_samples_split = [2, 3, 4]
= Best: 0.931847 using {'criterion': 'log_loss', 'max_depth': 5, 'max_leaf_nodes': 10}

For Random Forest Classifier:
- n_estimators = [10, 100, 1000]
- criterion = ['gini', 'entropy', 'log_loss']
= Best: 0.962435 using {'criterion': 'log_loss', 'max_features': 'log2', 'n_estimators': 100}

<img width="512" alt="Screenshot 2022-12-29 at 14 30 17" src="https://user-images.githubusercontent.com/82876331/209907935-63254bf0-18ba-4e28-bbad-1ef5baf36386.png">
