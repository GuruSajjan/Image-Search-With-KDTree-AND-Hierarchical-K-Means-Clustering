# Image-Search-With-KDTree-AND-Hierarchical-K-Means-Clustering
__Task :__
* Searching for simillar appearance images in 60000 images and selecting top-k simillar images for given test image.
  
__Data Set :__
* The MNIST dataset is a collection of 28x28 pixel grayscale images of handwritten digits (0 through 9).

__Here I try to implement and apply two alogithms :__
1. KD-Tree
2. Hierarchical K-Means Clustering
   
__Libraries used :__
1. Numpy (Linear algebra)
2. Matplotlib (for ploting result images and test image)
3. Tensorflow.keras.datasets (for downloading dataset)

## 1) KD-Tree 
__Training Phase :__
1. Convert image to vector 28x28 --> 784x1
2. Apply PCA to reduce dimensions 784x1 --> dx1 (where d < 784) Learn meanvector of size 784x1 and eigen vectors matrix of size 784xd.
3. Construct KD-Tree using dx1 vector representations and Learn and store parameter(Median) at each internal nodes of tree and create binary hash from root to each leaf node.

(please look into code for implemetation of KD-Tree algo)

![KD-Tree](https://github.com/GuruSajjan/Image-Search-With-KDTree-AND-Hierarchical-K-Means-Clustering/assets/49277337/4bb3fa7f-6e25-47ba-aea0-6aecfb07a0df)

__Testing Phase :__
1. Convert given test-image to vector 28x28 --> 784x1.
2. Use PCA parameters i.e mean vector and Eigen-vectors matrix to convert 784x1 --> dx1 vector.
3. Use KD-Tree parameter(Median) at each node from root till reaching one of the leaf node of KD-Tree.
4. In each leaf node we might have around 2500 to 3500 simillar appearance images (out of 60000 images).
5. To select top-k simillar images we can use cosine simillarity between test images and all images in that leaf node. 

![KD-Tree-Test](https://github.com/GuruSajjan/Image-Search-With-KDTree-AND-Hierarchical-K-Means-Clustering/assets/49277337/c845cbf3-f049-48cc-9a1b-bf3bffa29590)

__Result of KD-Tree on randomly selected test images :__

![KD-Tree-Result](https://github.com/GuruSajjan/Image-Search-With-KDTree-AND-Hierarchical-K-Means-Clustering/assets/49277337/52ca23a7-d3d3-4fd1-ad89-0b84ed62b650)

## 2)Hierarchical K-Means-Clustering

