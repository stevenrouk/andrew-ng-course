# Week 1 at a High Level

Let's say we have some regression problem, like predicting the price of a house based on how big the house is (in square feet). We solve this by finding a "hypothesis" function where we can plug in the size of the house and get out a number of what we think the price will be.

In mathy language, we want a function h: X --> Y.

So how do we choose the type of function we want for h? There are an infinite number of functions, which ones do we look at? For now, we're just going to make the choice of a simple linear function with only one variable, like a y = mx + b kind of thing.

In mathy language, we'll be doing univariate linear regression. h(x) = theta_0 + theta_1 * x

Alright, so we just chose a simple linear function for now, but that function has some parameters we need to fill in, which are the parts of our equation we can change: in traditional terms, those would be our 'm' and 'b', and in our new format we're calling those 'theta_0' and 'theta_1'.

How do we know if our function is good or not for certain parameters we choose? We'll define some "cost function", which is a measure of how much our function is off. In other words, how bad are our predictions? Then we minimize that function.

In mathy language, we define a cost function of our hypothesis function parameters J(theta_0, theta_1), then we minimize that function. For linear regression, "mean squared error" (MSE) is a good choice of cost function.

So we have a cost function that determines how bad our hypothesis is. How do we minimize that cost function? Gradient descent! It's an algorithm for iteratively minimizing a function by picking some values for our parameters, calculating the cost function using those parameters, then seeing how we need to tweak each of our parameters to get a slightly smaller cost function value the next time. If you imagine the cost function as a bowl, we want to pick the next parameters such that we're going slightly more towards the middle of the bowl. That middle of the bowl you can imagine as the minimum of our cost function, which means we will have picked the best hypothesis function we can.

In mathy language, we calculate the partial derivatives of the cost function in order the direction of "greatest slope", then we move in the direction of greatest decrease in the cost function, and repeat until convergence. (Which will be the opposite direction of the direction of greatest increase.) This means a simultaneous update of our parameters based on the partial derivatives. The paramater alpha here in the "learning rate", which is how big of a step we take. theta_j := theta_j - alpha * partial_deriv_j(J(theta_0, theta_1))