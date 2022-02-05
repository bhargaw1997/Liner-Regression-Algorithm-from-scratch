# Liner-Regression-Algorithm-from-scratch
Liner Regression Algorith from scratch

This assignment shows how we can extend ordinary least squares regression, which uses the hypothesis class of linear regression functions, to non-linear regression functions modeled using polynomial basis functions and radial basis functions. The function we want to fit is  𝑦𝗍𝗋𝗎𝖾=𝑓𝗍𝗋𝗎𝖾(𝑥)=6(sin(𝑥+2)+sin(2𝑥+4)) . This is a univariate function as it has only one input variable. First, we generate synthetic input (data)  𝑥𝑖  by sampling  𝑛=750  points from a uniform distribution on the interval  [−7.5,7.5] .

1. Regression with Polynomial Basis Functions.

This problem extends ordinary least squares regression, which uses the hypothesis class of linear regression functions_, to _non-linear regression functions modeled using polynomial basis functions. In order to learn nonlinear models using linear regression, we have to explicitly transform the data into a higher-dimensional space. The nonlinear hypothesis class we will consider is the set of  𝑑 -degree polynomials of the form  𝑓(𝑥)=𝑤0+𝑤1𝑥+𝑤2𝑥2+...+𝑤𝑑𝑥𝑑  or a linear combination of polynomial basis function.

The monomials  {1,𝑥,𝑥2,...,𝑥𝑑}  are called basis functions, and each basis function  𝑥𝑘  has a corresponding weight  𝑤𝑘  associated with it, for all  𝑘=1,...,𝑑 . We transform each univariate data point  𝑥𝑖  into into a multivariate ( 𝑑 -dimensional) data point via  𝜙(𝑥𝑖)→[1,𝑥𝑖,𝑥2𝑖,...,𝑥𝑑𝑖] . When this transformation is applied to every data point, it produces the Vandermonde matrix

2. Regression with Radial Basis Functions

In the previous case, we considered a nonlinear extension to linear regression using a linear combination of polynomial basis functions, where each basis function was introduced as a feature  𝜙(𝑥)=𝑥𝑘 . Now, we consider Gaussian radial basis functions of the form:

𝜙(𝐱)=𝑒−𝛾(𝑥−𝜇)2 ,
whose shape is defined by its center  𝜇  and its width  𝛾>0 . In the case of polynomial basis regression, the user's choice of the dimension  𝑑  determined the transformation and the model. For radial basis regression, we have to contend with deciding how many radial basis functions we should have, and what their center and width parameters should be. For simplicity, let's assume that  𝛾=0.1  is fixed. Instead of trying to identify the number of radial basis functions or their centers, we can treat **each data point as the center of a radial basis function**.

This transformation uses radial basis functions centered around data points  𝑒−𝛾(𝑥−𝑥𝑖)2  and each basis function has a corresponding weight  𝑤𝑖  associated with it, for all  𝑖=1,...,𝑛 . We transform each univariate data point  𝑥𝑗  into into a multivariate ( 𝑛 -dimensional) data point via  𝜙(𝑥𝑗)→[...,𝑒−𝛾(𝑥𝑗−𝑥𝑖)2,...] . When this transformation is applied to every data point, it produces the radial-basis kernel.

