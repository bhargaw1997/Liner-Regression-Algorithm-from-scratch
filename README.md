# Liner-Regression-Algorithm-from-scratch
Liner Regression Algorith from scratch
This assignment shows how we can extend ordinary least squares regression, which uses the hypothesis class of linear regression functions, to non-linear regression functions modeled using polynomial basis functions and radial basis functions. The function we want to fit is  𝑦𝗍𝗋𝗎𝖾=𝑓𝗍𝗋𝗎𝖾(𝑥)=6(sin(𝑥+2)+sin(2𝑥+4)) . This is a univariate function as it has only one input variable. First, we generate synthetic input (data)  𝑥𝑖  by sampling  𝑛=750  points from a uniform distribution on the interval  [−7.5,7.5] .

1. Regression with Polynomial Basis Functions.
This problem extends **ordinary least squares regression**, which uses the hypothesis class of _linear regression functions_, to _non-linear regression functions_ modeled using **polynomial basis functions**. In order to learn nonlinear models using linear regression, we have to explicitly **transform the data** into a higher-dimensional space. The nonlinear hypothesis class we will consider is the set of $d$-degree polynomials of the form $f(x) \, = \, w_0 + w_1 x + w_2 x^2 + ... + w_d x^d$ or **a linear combination of polynomial basis function**:

<div align="center">
$
        f(x) = [w_0, \, w_1,\, w_2 \, ..., w_d]^T \left[ \begin{array}{c} 1 \\ x \\ x^2 \\ \vdots \\ x^d\end{array} \right]
$.
</div>

The monomials $\{ 1, \,  x, \, x^2, \, ..., \,  x^d\}$ are called **basis functions**, and each basis function $x^k$ has a corresponding weight $w_k$ associated with it, for all $k \, = \, 1, ..., d$. We transform each univariate data point $x_i$ into into a multivariate ($d$-dimensional) data point via  $\phi(x_i) \rightarrow [1, \,  x_i, \, x_i^2, \, \, ..., \,  x^d_i]$. When this transformation is applied to every data point, it produces the **Vandermonde matrix**:

<div align="center">
$
        \Phi \, = \,
        \left[
        \begin{array}{ccccc}
            1 &  x_1 & x_1^2 & ... &  x_1^d\\
            1 &  x_2 & x_2^2 & ... &  x_2^d\\
            \vdots &   \vdots & \vdots & \ddots &  \vdots\\
            1 &  x_n & x_n^2 & \cdots &  x_n^d\\
        \end{array}
        \right]
$.
</div>
