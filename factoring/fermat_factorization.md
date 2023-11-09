# Fermat's Factorization

For an odd composite number $N=ab$, $\lvert b-a\rvert$ is an even number.

Let's define $k=\frac{\lvert b-a\rvert}{2}$, $m = \frac{a+b}{2}$.

Then we get

$$
N = ab = (m-k)(m+k) = m^2 - k^2
$$

Therefore, $m^2-N=k^2$ should be a perfect square number. Then, we can consider the following pseudo-code for factoring.

```
FermatFactor(N): // N should be odd
    a ← ceiling(sqrt(N))
    b2 ← a*a - N
    repeat until b2 is a square:
        a ← a + 1
        b2 ← a*a - N 
     // equivalently: 
     // b2 ← b2 + 2*a + 1 
     // a ← a + 1
    return a - sqrt(b2) // or a + sqrt(b2)
```

Since `b2` increases around $2\sqrt{N}$ at a time, the approximate time complexity of this algorithm is $\frac{k^2}{2\sqrt{N}}$.

Therefore, fermat's factorization is very useful when the difference between two paired factors is very small.

---
Reference

\[1\] https://en.wikipedia.org/wiki/Fermat%27s_factorization_method