Distances
---------

Notions of distance, some make more sense than others depending
on the situation.

Distances must have the following properties (Axioms):
  * distances >= 0
  * d(x,x) = 0
  * d(x,y) = d(y,x) Symmetry
  * d(x,y) <= d(x,z) + (z,y) AKA Triangle Inequality

## Types of Distances

1. The L norm distances
  The Lr norm is defined as follows: (x1^r + x2^r + .... + xn^r)^(1/r)
  L1 norm = x1 + x2 + .... + xn
  L2 norm = (x1^2 + x2^2 + .... + xn^2)^(1/2)

2. Jaccard distance for sets
  1 - Jaccard similarity

3. Cosine distance for vectors
  Angle between the vectors.

4. Edit distance for strings
  Number of inserts/deletes to change one string to another.

5. Manhattan distance
  Think of a triangle with points (a,b), (b,c), (a,c).
  (a,c) is the hypotenuse. The manhattan distance is
  (a,b) + (b,c).
  No shortcuts

6. Hamming Distance for bit vectors
  Number of positions in which they differ.
