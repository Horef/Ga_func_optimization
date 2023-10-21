# Ga_func_optimization
What is possibly the least effective way to find a maximum of a function? With GAs!

## Please Note
1. I have actually built the algorithm in such a way that you can actually find points where function equals to any value (check comments in the code).
2. This code (in the way it is currently implemented) **will only work for scalar functions**.
If you wish to use it for vector functions, you need to create an intermediate utility function which will convert the output vector to a single number.
3. In continuation to the previous point, it will only work for functions of form f:R^n -> R. If you have a function g:C^n -> R, you will have to implement h:C^n -> R^2n, such g=f(h).

## The Algorithm
The algorithm is actually pretty simple, and works in a following way:

### Preliminary
1. Each agent will be represented as a vector in R^n.

### Steps
