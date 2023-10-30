# Principal Component Analysis (PCA)

Welcome to the PCA tutorial! In this guide, you will learn all about Principal Component Analysis and its practical applications.

## Table of Contents
1. [What is PCA](#What_is_PCA)
2. [Need for PCA](#need-for-pca)
    - [Curse of Dimensionality](#curse-of-dimensionality)
    - [Multicollinearity](#multicollinearity)
3. [Understanding PCA](#understanding-pca)
    - [Variance](#variance)
    - [Orthogonality](#orthogonality)
    - [Eigenvalues and Eigenvectors](#eigenvalues-and-eigenvectors)
4. [Steps in PCA](#steps-in-pca)
    - [Standardization](#standardization)
    - [Covariance Matrix](#covariance-matrix)
    - [Eigenvalue Decomposition](#eigenvalue-decomposition)
    - [Selecting Principal Components](#selecting-principal-components)
    - [Transform Data](#transform-data)
5. [Explained Variance](#explained-variance)
    - [Explained Variance Ratio](#explained-variance-ratio)
    - [Scree Plot](#scree-plot)
6. [Practical Applications](#practical-applications)
    - [Dimensionality Reduction](#dimensionality-reduction)
    - [Noise Reduction](#noise-reduction)
    - [Data Compression](#data-compression)
    - [Anomaly Detection](#anomaly-detection)
7. [Limitations](#limitations)
    - [Loss of Interpretability](#loss-of-interpretability)
    - [Non-linear Relationships](#non-linear-relationships)
    - [Data Scaling](#data-scaling)
8. [Alternatives to PCA](#alternatives-to-pca)
    - [Non-linear Dimensionality Reduction Techniques](#non-linear-dimensionality-reduction-techniques)
    - [Feature Selection](#feature-selection)
9. [Practical on Datasets](#Practical-on-Datasets)
10. Before Applying PCA, Predict the dataset with Linear Regression and Decision Tree.
    - [Drop ID columns](#drop-id-columns)
    - [Train Test Split](#train-test-split)
    - [Linear Regression Model](#linear-regression-model)
    - [Decision Tree Regressor Model](#decision-tree-regressor-model)
11. Apply PCA on Dataset
    - [Data Standardization](#data-standardization)
    - [Cumulative Explained Variance Ratio to Select perfect n_Components](#cumulative-explained-variance-ratio-to-select-perfect-n-components)
    - [Decision Tree Model On PCA Dataset](#decision-tree-model-on-pca-dataset)
    - [PCA Decision Tree Metrics](#pca-decision-tree-metrics)
    - [Comparison PCA Decision Tree Metrics](#comparison-pca-decision-tree-metrics)
    - [Comparison Decision Tree Metrics without PCA](#comparison-decision-tree-metrics-without-pca)
12. PCA with Digit Dataset
    - [Sample Digits from the Digit Dataset](#sample-digits-from-the-digit-dataset)
    - [Standardize the data](#standardize-the-data)
    - [Perform PCA](#perform-pca)
    - [Explained Variance Ratio](#explained-variance-ratio)
    - [Plot the PCA results](#plot-the-pca-results)

# 1. What is PCA

**Understanding Principal Component Analysis (PCA)**

*Introduction to PCA - Simplified Explanation*

Imagine you have a collection of data, like the measurements of various parts of a car. You've got data on the length, width, height, weight, and maybe even the horsepower of different car models. Now, you want to understand this data better, but there's a problem: too many features or dimensions to deal with. That's where PCA comes in.

**PCA as a Data Simplifier**

PCA is like having a magic tool that helps you simplify your data. It takes all these different measurements and tells you which ones are most important. In other words, it helps you figure out what's really going on in your data without all the complexity.

**Reducing Complexity**

The first thing PCA does is to find a new set of measurements that are related to the original ones but are much simpler. These new measurements are called "principal components." Instead of dealing with many features, you'll work with a smaller number of principal components.

**Variance and Information**

PCA figures out which original measurements carry the most "information" or "variance" in your data. Think of variance as a measure of how much your data varies. So, the measurements that change a lot from one car to another are important, and PCA finds those for you.

**Orthogonality and Independence**

Another cool thing about PCA is that it makes sure the principal components are not just simplified but also independent of each other. In other words, they don't carry the same information, so you avoid redundancy.

**Application in Data Science**

Why is this helpful in data science? Well, you can use PCA for various things:

- **Dimensionality Reduction**: If you have too many features, PCA helps you focus on the most crucial ones, making your analysis easier.

- **Visualization**: It can help you plot your data in a way that's easier to see patterns.

- **Noise Reduction**: If your data has some noisy measurements, PCA can clean that up.

In a Nutshell

Think of PCA as a way to look at your data from a different, simpler angle. It helps you focus on what really matters and understand your data better, making it a powerful tool in data analysis and machine learning.

**How PCA Works**

PCA works by finding the directions in the data where the variance is highest. These directions are the principal components, and they are orthogonal to each other, meaning they are uncorrelated. The first principal component captures the most variance, the second captures the second most, and so on.

**Example**

Let's consider a simple example with two variables, X and Y:

X Y
1 2
2 3
3 3
4 4
5 5



**Step 1: Standardize Data**

First, we standardize the data by subtracting the mean and dividing by the standard deviation for both X and Y.

**Step 2: Calculate Covariance**

Next, we calculate the covariance matrix. In this case, it is:

| 0.5 0.5 |

| 0.5 1.0 |



**Step 3: Find Eigenvalues and Eigenvectors**

We find the eigenvalues and eigenvectors of the covariance matrix. In this case, we have one eigenvalue of 0.25 and an eigenvector of [1, 2].

**Step 4: Select Principal Components**

The first principal component is the eigenvector [1, 2].

**Step 5: Transform Data**

We can project the original data onto the first principal component. This results in a new dataset with reduced dimensionality.




