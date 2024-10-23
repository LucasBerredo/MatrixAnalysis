# MatrixAnalysis
A collection of tools for performing numerical matrix analysis. Includes some exact solvers, numerical solvers, other tools and some applications (particularly finite difference methods for PDEs).
All code is provided in MATLAB script and/or Python. Feel free to contact for any inquiries!

## Exact solvers


## Iterative solvers


## General tools

### Gram-Schmidt
Gram-Schmidt orthonormalization. Based on the Gram-Schmidt theorem for Linear Algebra, where one can find an orthonormal basis, given any other basis, on a K-vector space with a given scalar product.

Usage:
- Let M be a real or complex square matrix, where the columns represent basis vectors.
- The program returns another matrix Q, where the columns represent are the orthonormal basis.

Warnings / errors:
The program will output an error if any of the following criteria are **NOT** met
- The matrix M has non real or complex numbers.
- The matrix M is not square.
- The matrix M is not of maximal range (i.e., is singular).


### Schur 
Schur factorization. Given a matrix A, finds an upper triangular matrix T and a unitary matrix P such that $A=P^{-1}AP=P^*AP$.

Usage:
- Let M be a real or complex square matrix.
- The program returns two matrices, T and P, following the conditions outlined above.

Warnings / errors:
- The program will error if the matrix is not square
- The program will error for non-numerical matrices

Note:
- Currently, the MATLAB function does not support compiling, as it uses the symbolic math toolbox. If necessary, please consider using fastEIGS().
- 

## Applications
