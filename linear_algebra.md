linear algebra
==============

## Intro

Note: Fix this up with LateX

Ax = b

A is a matrix
x,b are vectors

Linear algebra is about solving these system of linear equations. Solve for b.

## Identity and Inverse

inv(A) is the inverse of A.
I is the identity matrix.

I = inv(A)A

Ax = b
inv(A)Ax = inv(A)b
Ix = inv(A)b
x = inv(A)b

The solution of the system depends on the inverse existing.

## Linear dependence, span and rank

In order for inv(A) to exist, the system must have exactly one solution
for every b. In general a system can have either 1, 0 or infinitely many
solutions.

To see why it's not possible for a system to have more than 1 solution but less
than infinity suppose:

z = ax + (1-a)y

x, y are solutions

for any real number a, z will also be a solution for the very same system as x,y.

### Linear combination and Span

A Linear combination can be written as c1 x v1 + c2 x v2 + .... + cn x vn.
c1..cn are real constants and v1..vn are vectors.

The **span** is the set of points obtainable by linear combination of the original vectors.

For this we can see determining Ax = b amounts to testing whether b is in the span of the columns
of A. This is called the _column space_ or the _range_ of A.

### Linear dependence

A set of vectors is said to be _linearly independent_ if no vector in the set is a linear combination of the other
vectors in the set, the new vector does not add any points to the set's span.

In order for a matrix to have only one solution for every b, it's columns must be linearly independent and the number
of rows = num of columns. This is known as a _singular_ matrix.

If A is not square or is square but singular, it can still be possible to solve the equation. 
However, we can not use the method of matrix inversion to ﬁnd the solution.

## Norms

A norm measures the size of a vector. Norms satisfy the following properties:

1. f(x) = 0 => x = 0 vector
2. f(x+y) <= f(x) + f(y) (the triangle inequality)
3. for all real a f(ax) = abs(a) f(x)

The l1 norm is commonly used in machine learning when the difference between 0 and nonzero elements is very important.

## Special Matrices and vectors

### Diagonal Matrix

Important because they're very computationally efficient.

Inverse exists if no nonzero element on the diagonal. In this case the inverse is simply 1/vi where vi is the element.

### Symmetric Matrix

inv(A) = A

### Unit vectors

A vector with a unit norm.

### Orthogonal vectors

The dot product of the vectors is equal to 0.

### Orthonormal vectors

Unit + Orthogonal.

### Orthogonal matrix

trans(A) A = A trans(A) = I

implies inv(A) = trans(A)

Really interesting because it's super easy to compute the transpose. So the inverse of an orthogonal matrix is
super easy to compute.

## Eigendecomposition

An eigenvector of a square matrix A is a non-zero vector v such that multiplication byA alters only the scale of v:

A**v** = λ**v**

The scalar λ is known as the eigenvalue corresponding to this eigenvector.

 We can construct a matrix **A** with eigenvectors {v(1), . . . , v(n)} and corresponding eigenvalues {λ1, . . . , λn} by 
 concatenating the eigevectors into a matrix **V** , one columnper eigenvector, and concatenating the eigenvalues into a vector λ. 
 Then the matrix
 
 **A** = **V** diag(λ)**V**−1

 has the desired eigenvalues and eigenvectors. if we make **V** an orthogonal matrix, then we can think of **A** as
 scaling the space by λi in the direction v(i).

Every real symmetric matrix can be decomposed into an expression using only real-valued eigenvectors and eigenvalues.

A = Q^trans(T)

Q is the orthogonal matrix and ^ is the diagonal matrix.

### Interesting eigendecomposition facts

1. The matrix is singular iff any eigenvalue is 0.
2. The maximum value of f within the constraint region is the max eigenvalue, min value of f in the min eigenvalue.
3. Matrix whose eigenvalues are all > 0 is called positive definite.
4. Matrix whose eigenvalues are all >= 0 is called positive semidefinite.
5. Matrix whose eigenvalues are all < 0 is called negative definite.
6. Matrix whose eigenvalues are all <= 0 is called negative semidefinite.

Positive semidefinite matrices guarantee for all x,trans(x): Ax >= 0.

Positive definite matrices additionally guarantee that trans(x)Ax = 0 => x = 0.

## The trace operator

The trace gives the sum of all the diagonal entries of a matrix.

Useful in simplifying equation notation.

## Determinant

A function mapping matrices to real scalars. The determinant is equal to the product of
a matrix's eigenvalues. The absolute value of the determinant can be thought of as a measure
of how much multiplication by the matrix expands or contracts space.

