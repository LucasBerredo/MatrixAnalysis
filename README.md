# MatrixAnalysis
A collection of tools for performing numerical matrix analysis. Includes some exact solvers, numerical solvers, other tools and some applications (particularly finite difference methods for PDEs).
All code is provided in MATLAB script and/or Python. Feel free to contact for any inquiries!


## General tools

### Gram-Schmidt
Gram-Schmidt orthonormalization. Based on the Gram-Schmidt theorem for Linear Algebra, where one can find an orthonormal basis, given any other basis, on a K-vector space with a given scalar product.

Usage:
- Let M be a real or complex square matrix, where the columns represent basis vectors.
- The program returns another matrix Q, where the columns represent are the orthonormal basis.

Warnings / errors:
The program will output an error if any of the following criteria are **NOT** met.
- The matrix M has non real or complex numbers.
- The matrix M is not square.
- The matrix M is not of maximal range (i.e., is singular).


### Pseudo-inverse
Finds the pseudo-inverse of a matrix. If square, the matrix is just its inverse. If not, the program returns the closest matrix. This is useful for solution of overdetermined systems, as the pseudoinverse is involved in the minimal error solution for the 2-norm.

Usage:
- Let M be a numerical matrix.
- The program returns another matrix Q, the pseudoinverse of M.

Warnings / errors:
- Since the program is based on the SVD decomposition, see its error section.

Note:
- Since the program is based on the SVD decomposition, see its notes section.

## Factorizations

### Schur 
Schur factorization. Given a matrix A, finds an upper triangular matrix T and a unitary matrix P such that $A=P^{-1}AP=P^*AP$.

Usage:
- Let M be a real or complex square matrix.
- The program returns two matrices, T and P, following the conditions outlined above.

Warnings / errors:
- The program will error if the matrix is not square
- The program will error for non-numerical matrices

Note:
- Currently, the MATLAB function does not support compiling, as it uses the symbolic math toolbox. If necessary, please consider using fastEIGS(), which may introduce some error.


### SVD
Singular Value Decomposition. Given any matrix, finds the singular values. Also computes $U\in\mathcal{M}_{n\times n}(\mathbb{K}), V\in\mathcal{M}_{m\times m}(\mathbb{K})$ and $\Sigma\in\mathcal{M}_{m\times n}(\mathbb{R})$ such that $A=V\Sigma U^*$, where $^*$ is the complex conjugate. $\Sigma$ is a diagonal matrix of the singular values.

Usage:
- Let M be a real or complex square matrix.
- The program returns three matrices, U, V, and Sigma that follow the conditions above.

Warnings / errors:
- The program will error for non-numerical matrices

Note:
- If one just wishes to calculate the singular values, the code can be halted at the line ```singular_values = sqrt(diag(D))```, and change the return values.
- Since it requires the Schur factorization, the MATLAB program will not compile. If necessary, consider using fastEIGS, while assuming some error.



## Applications
