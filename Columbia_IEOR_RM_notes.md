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

What are the drawbacks? This is a static problem, we are not accounting for changes in demand as a function of time *e.g.*, seasonality. Here we also treat $$d(p)$$ as determinstic, however, in reality, this might be stochastic in nature. 










