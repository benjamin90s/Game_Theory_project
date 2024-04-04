# Game_Theory_project
PCA as NASH equilibrium

In this project, we have implemented the algorithm described in the research paper "EIGENGAME: PCA AS A NASH EQUILIBRIUM
" on a smaller dataset. The steps and results of the code are summarized below:

Steps:

1)**Image Processing**: The code starts by loading an image and converting it to a grayscale numpy array. This is done using the PIL library.

2)**EigenGame Method for PCA**: The core of the code implements the EigenGame approach to calculate the first two principal components of the image:
i)A model function computes the utility for an eigenvector, taking into account the reward (alignment with maximum variance) and the penalty (orthogonality to previous eigenvectors).
ii)An update function uses the gradient of the utility to iteratively adjust the eigenvector, maximizing the utility function.
iii)The eigenvectors are calculated sequentially with multiple iterations to ensure convergence.

3)**Comparison with NumPy's PCA**: For validation, the code compares the results of the EigenGame PCA with the results obtained using NumPy's linear algebra functions to perform a standard PCA. This includes comparing both the eigenvalues and the alignment of eigenvectors.

**Results**:

1)**Eigenvalues Comparison**:

The eigenvalues obtained from the EigenGame method are printed and compared with those obtained from NumPy. The eigenvalues are very close, indicating that the EigenGame method is accurate.

2)**Eigenvector Alignment**:

The dot products between the corresponding eigenvectors from the EigenGame method and the NumPy PCA are calculated to assess their alignment. The dot products are close to 1, indicating a high degree of alignment.

3)**Dimensionality Reduction and Visualization**:

The image data is projected onto the two principal components, effectively reducing its dimensionality.
A scatter plot of the first two principal components is then generated, allowing for visual assessment of the data's structure in this reduced space.

4)**Scatter Plot Analysis**:

The scatter plot shows the data points distributed primarily along the first principal component, with the second principal component capturing a smaller but still significant variation.
The data points do not exhibit distinct clustering, which suggests no clear separable classes in the image data or a continuous variation.

**Summary**:

The code successfully demonstrates the implementation of PCA using the EigenGame method, validated against NumPy's PCA implementation. The results indicate that the EigenGame approach is accurate, with eigenvectors that align closely with those obtained from the traditional PCA. The dimensionality reduction is visualized through a scatter plot, showing how the data is represented in the space of the first two principal components. This serves as a useful tool for understanding and working with high-dimensional data in a more manageable form.
