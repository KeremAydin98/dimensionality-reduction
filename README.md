# dimensionality-reduction
## Understanding dimensionality reduction methods


Dimensionality Reduction can be defined as lowering the dimension of a data set with minimum loss of information. The change in variance is used as a loss since the information gets lost when the variance changes. There are many methods for dimensionality reduction.

Two definitions should be thought in order to explain the dimensionality reduction methods. These are:

* Projection
* Manifold

### 1. Projection

Projection is exactly what you think it is. A plane(depends on the number of dimensions) is fitted into a data set(how it is fitted will be explained later) and the data points are lowered down onto the plane in order to lower the dimension of the dataset. I think it is better to be observed than be thought.

Before projection

![resim](https://user-images.githubusercontent.com/77073029/187265031-5b8125b0-038b-48db-9a06-ebacfae5eee0.png)

After projection

![resim](https://user-images.githubusercontent.com/77073029/187265061-ac3cac72-cc8d-45ac-a4fe-f8d6192bc090.png)

### 2. Manifold

Simply, 2D manifold is a 2D shape that can be bent and twisted in a higher dimensional space. More generally a d-dimensional manifold is a part of an n-dimensional space that locally resembles a d-dimensional hyperplane. Many dimensionality reduction algorithms work by modelling the manifold on which training instances lie.

PCA is by far the most commonly used algorithm for dimensionality reduction. PCA works by projecting data points onto a hyperplane and hyperplane is created with the minimization of the mean squared error between data points and projected data points. PCA can be implemented by using the Scikit-learn library. There are a few PCA algorithms: regular PCA, incremental PCA, randomized PCA and finally kernel PCA. 

We can choose which PCA algorithm we are going to use according to the properties of the data set. If the data set is a linearly separable then we can use regular PCA or randomized PCA since the Scikit-learn’s PCA will choose the fastest one by looking at the data. And if we want to fit the data on mini-batches when the data set is too large, therefore we won’t have to load the whole data set then fit it. This will dramatically increase our speed. Finally if the data set is not linearly separable then kernel PCA can be used, since kernel helps PCA to create non-linear hyperplanes(just like kernel SVM) to be projected on.

By the way the optimal hyperparameters of the PCAs can be calculated by using GridSearch function in the Scikit-learn library.

All the dimensionality reduction techniques I have explained uses projection rather than a manifold. So it is better to finish off by explaining a dimensionality reduction which uses a manifold. 

LLE algorithm first measures the linear distance of each data points to with their closest neighbors and then lowers the dimension with minimum loss of information. This algorithm can even reduce dimensions of the Swiss roll data set.
