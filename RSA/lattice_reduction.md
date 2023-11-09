# Lattice Reduction

Lattice Reduction algorithms, such as LLL, provide an approximate solution of SVP.

If `d` is small enough, the following 2-dimensional lattice has a shortest vector $(ed-kN,d\sqrt{N})$.

$$
\begin{bmatrix}
e & \sqrt{N} \\
N & 0
\end{bmatrix}
$$

This can be implemented with the following code:

```python
s = Integer(N^0.5)
m = matrix([[e,s],[N,0]])
d_candidate = [m.LLL()[i,1]//s for i in range(2)]
```