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
(All of the steps are quite abstract, so check the code)
1. Create a given number of agents from the square defined around center of the axis.
2. Calculate the utility (closeness to a certain point, infinity, or -infinity) of each agent.
    1. Utulity function has to be strictly positive, so shift the utility if needed. For example, if you are trying to find maximum of a function and some points are negative, increase all the utilities by a contant, such that every utility will be greater than 5 (chosen arbitrary).
3. Calculate the probability of reproduction for each agent as its utility divided by the total (sum of all) utility.
4. Until you have created the same number of new agents as there were previously:
    1. Order all agents by their probability (break ties arbitrarily) (each probability defines a section) and generate a number from uniform (0,1).
    2. Pick the agent to which this number corresponds.
    3. Roll again and pick another agent.
    4. Roll to check for the probability of crossover.
        1. If true, roll uniform on length of the vector and create two new crossed agents.
        2. Otherwise put both agents "as is" to the new array.
5. Go over all agents and for each entry of each vector roll uniform to find the probability of mutation.
    1. If true, roll normal with expected value of the number you mutate, and predefined variance.
    2. Otherwise do nothing.
6. Repeat until stop condition is reached.