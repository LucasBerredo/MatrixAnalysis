# MatrixAnalysis
A collection of tools for performing numerical matrix analysis. Includes some exact solvers, numerical solvers, other tools and some applications (particularly finite difference methods for PDEs).
All code is provided in MATLAB script and/or Python. Feel free to contact for any inquiries!


## General tools

### Gram-Schmidt
<details>
<summary>Gram-Schmidt orthonormalization. Based on the Gram-Schmidt theorem for Linear Algebra, where one can find an orthonormal basis, given any other basis, on a K-vector space with a given scalar product. </summary>


Usage:
- Let M be a real or complex square matrix, where the columns represent basis vectors.
- The program returns another matrix Q, where the columns represent are the orthonormal basis.

Warnings / errors:
The program will output an error if any of the following criteria are **NOT** met.
- The matrix M has non real or complex numbers.
- The matrix M is not square.
- The matrix M is not of maximal range (i.e., is singular).
</details>

### Pseudo-inverse
<details>
<summary>Finds the pseudo-inverse of a matrix. If square, the matrix is just its inverse. If not, the program returns the closest matrix. This is useful for solution of overdetermined systems, as the pseudoinverse is involved in the minimal error solution for the 2-norm.</summary>


Usage:
- Let M be a numerical matrix.
- The program returns another matrix Q, the pseudoinverse of M.

Warnings / errors:
- Since the program is based on the SVD decomposition, see its error section.

Note:
- Since the program is based on the SVD decomposition, see its notes section.
</details>

### Regressive substitution
<details>
<summary>Given an upper triangular matrix T, and a column vector b, the program returns a vector x such that
$Ax=b$.</summary>

Usage:
- Given a real, upper triangular non singular matrix M and a column vector b
- Returns a real, column vector x such that
$Ax=b$.

Warnings / errors:
- The program will raise an error if the matrix is singular.
- The program will riase a warning if the matrix has elements outside of the upper triangle.

</details>

### Progressive substitution
<details>
<summary>Given a lower triangular matrix L, and a column vector b, the program returns a vector x such that
$Ax=b$.</summary>

Usage:
- Given a real, lower triangular non singular matrix M and a column vector b
- Returns a real, column vector x such that
$Ax=b$.

Warnings / errors:
- The program will raise an error if the matrix is singular.
- The program will riase a warning if the matrix has elements outside of the upper triangle.

</details>

### Fixed Point
<details>
<summary> Applies a fixed-point scheme to solve a system
$Ax=b$, up to a given tolerance of maximum number of iterations.</summary>

Usage:


Warnings / errors:


Note:
- While this program does work for any method, it is recommmended to use Jacobi, Gauss-Seidel or Kaczmarz methods.
  
</details>

## Solvers

### Gaussian elimination (pivoting and non-pivoting)
<details>
<summary>
Given a square matrix A, and a vector b, finds a solution x to the linear system 
$Ax=b$

</summary>

Usage:

- Let M be a real-valued non-singular matrix, and b a column vector.
- The program returns a column vector x that satisfies the system.

Warnings/errors:
- The program will raise an error if the matrix is singular
$\det A=0$.
- The program will raise an error if the matrix is not square.
- The program will raise a warning if at any point a diagonal zero is found.

Note:
- For most cases, the pivoting version would be quicker.
- Removing the last line and changing the output variable to M will return the final matrix.
- The program requires the regressive sustitution program.

</details>

### Jacobi 
<details>
<summary> </summary>

  
</details>


### Gauss-Seidel
<details>
<summary> </summary>

  
</details>


### Relaxation
<details>
<summary> </summary>
  
</details>



## Factorizations

### Schur 
<details>
<summary>Schur factorization. Given a matrix A, finds an upper triangular matrix T and a unitary matrix P such that 
$A=P^{-1}AP=P^*AP$
.</summary>

Usage:
- Let M be a real or complex square matrix.
- The program returns two matrices,
$T$
and
$P$, following the conditions outlined above.

Warnings / errors:
- The program will error if the matrix is not square.
- The program will error for non-numerical matrices.

Note:
- Currently, the MATLAB function does not support compiling, as it uses the symbolic math toolbox. If necessary, please consider using fastEIGS(), which may introduce some error.
</details>

### SVD
<details>
<summary>Singular Value Decomposition. Given any matrix, finds the singular values. Also computes 
$U\in\mathcal{M}_{n\times n}(\mathbb{K}), V\in\mathcal{M}_{m\times m}(\mathbb{K})$ 
and 
$\Sigma\in\mathcal{M}_{m\times n}(\mathbb{R})$
such that 
$A=V\Sigma U^*$
, where 
$^*$
is the complex conjugate. 
$\Sigma$
is a diagonal matrix of the singular values.</summary>

Usage:
- Let M be a real or complex square matrix.
- The program returns three matrices, U, V, and Sigma that follow the conditions above.

Warnings / errors:
- The program will error for non-numerical matrices

Note:
- If one just wishes to calculate the singular values, the code can be halted at the line ```singular_values = sqrt(diag(D))```, and change the return values.
- Since it requires the Schur factorization, the MATLAB program will not compile. If necessary, consider using fastEIGS, while assuming some error.
</details>

### Cholesky
<details>
<summary> </summary>

  
</details>


## Applications

### Eigenvalues
<details>
<summary> </summary>
  
</details>


### Iterative inverse
<details>
<summary> </summary>
  
</details>
