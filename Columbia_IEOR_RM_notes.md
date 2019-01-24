## Columbia IEOR 4601 Dynamic Pricing & Revenue Management
###  Lecture 1 (Jan. 24, 2019)
The class starts with a poll, that VA asks as a company, should it increase/decrease its price as much as possible? Of course, the answer is no. The points to consider include: cost, market share, competitors' prices etc.

We will start with a simple model, that there is **no competition**. It's called **staic pricing**.

#### Static Pricing
Assumptions: 

1. There is no other competitors, we are the only seller. 
2. We only sell one product. 
3. The expected demand $$d(p)$$ is a decreasing function of the price $$p$$.

Examples that violate these assumptions: luxury product. 

What are the common $$d(p)$$ functions are used? The simplest is the linear function: 

$$d(p) = a - b p.$$

Another common example is loglinear:

$$d(p) = a \exp({-bp}).$$

What's wrong with these simple models? For large $$p$$, things can go wild. As a rule of thumb, we should always remember that all models have limitations. As the statistician George Box [said](https://en.wikipedia.org/wiki/All_models_are_wrong): *All models are wrong, some are useful.* However, these simple models will get us somewhere, to start with.

The goal of the revenue optimizaion will then be: 

$$
p_\text{opt} = \underset{p}{\mathrm{argmax}}~{p \times d(p)}.
$$

This is called static price optimization problem. If we consider cost $$c$$, then we are solving: 

$$
p_\text{opt} = \underset{p}{\mathrm{argmax}}~{(p-c) \times d(p)}.
$$

Depending on the exact form of $$d(p)$$, one can then solve this optimization problem. If $$d(p)$$ is linear, then the optimization is trivial. 

What are the drawbacks? This is a static problem, we are not accounting for changes in demand as a function of time *e.g.*, seasonality. Here we also treat $$d(p)$$ as determinstic, however, in reality, this might be stochastic in nature. It also doesn't consider the absolute value of the demand (or supply).

#### Model fitting with least square
Let's take the linear demand model as an example. What do we need? We need previous demand and previous prices, such as $$(p_1, d_1), (p_2, d_2), ..., (p_N, d_N)$$. We want to find out the values of $$a, b$$. The approach is to minimize the loss function: 

$$
L = \sum_i (a - bp_i - d_i)^2.
$$

Instead of square error, we can minimize the absoluate error. If some data points are more important than others, we can assign larger weights to them. To keep the absolute values of $$a, b$$ small (to prevent overfitting), we can add regularization terms to the loss function. Then the cost function becomes: 

$$
C = \lambda(a^2 + b^2) + \sum_i (a - bp_i - d_i)^2.
$$

Here we just used the L2 regularization. More generally, if the data has the form $$(\textbf{x}_1, y_1), (\textbf{x}_2, y_2), ... (\textbf{x}_N, y_N)$$, where $$\textbf{x}_i$$ is a vector, then the cost function can be written as:

$$
C = \lambda ||\textbf{w}|| + \sum_i (\textbf{w}^T \textbf{x}_i - y_i)^2,
$$

where $$\textbf{w}$$ is a vector, and $$||\cdot||$$ is the [norm](https://en.wikipedia.org/wiki/Norm_(mathematics)). Depending on what norm is chosen, we can be dealing with [Lasso](https://en.wikipedia.org/wiki/Lasso_(statistics)) or [Rigde](https://en.wikipedia.org/wiki/Tikhonov_regularization) regression.

What are some **common pitfalls** of doing all these? You might not get any data, or you might not be able to have data points at different prices. If one only has one price point, there is nothing one can do. Also, again, this is static, and different data points may come from different time points (think seasonality, day-of-week effects). The demand might be aggregated over different duration, in which case one needs to normalize the data.  











