---
category: "[[Clippings]]"
author: "[[Bruno Magalhaes]]"
title: "Exponential Family of Distributions"
source: https://brunomaga.github.io/Exponential-Family-Distributions
clipped: 2024-04-18
published: 2019-03-20
topics: 
tags: [clippings]
---

On the [previous post](https://brunomaga.github.io/Bayesian-Linear-Regression), we saw that computing the Maximum Likelihood estimator and the Maximum-a-Posterior on a normally-distributed set of parameters becomes much easier once we apply the log-trick. The rationale is that since is an increasingly monotonic function, the maximum and minimum values of the function to be optimized are the same as the original function inside the operator. Thus, by applying the function to the solution, the normal distribution becomes simpler and faster to compute, as we convert a product with an exponential into a sum.

However, this is not a property of the Gaussian distribution only. In fact, most common distributions including the exponential, log-normal, gamma, chi-squared, beta, Dirichlet, Bernoulli, categorical, Poisson, geometric, inverse Gaussian, von Mises and von Mises-Fisher distributions can be represented in a similar syntax, making it simple to compute as well. To the set of such distributions we call it the **Exponential Family of Distributions**, and we will discuss them next.

### Detour: relationship between common probability distributions

Probability distributions describe the probabilities of each outcome, with the common property that the probability of all events adds up to 1. They can also be classified in two subsets: the ones described by a probability **mass function** if specified for discrete values, or probability **density functions** if described within some continuous interval. There are dozens (hundreds?) of different distributions, even though only 15 of them are often mentioned and used, and have some kind of relationship among themselves:

![](https://brunomaga.github.io/assets/Exponential-Family-Distributions/common_distributions.png)

15 most common probability distributions and their relationships. (source: post [Common probability distributions](https://medium.com/@srowen/common-probability-distributions-347e6b945ce4) from Sean Owen)

A bried summary of their relationship follows. For more details, check the original [post](https://medium.com/@srowen/common-probability-distributions-347e6b945ce4) from Sean Owen:

-   *Bernoulli and Uniform*: the uniform distribution yields equal probability to each discrete outcome e.g. a coin toss or a dice roll; the Bernoulli yields an unequal probability to two discrete outcomes as and , e.g. an unfair coin toss;
-   *Binomial and Hypergeometric*: the binomial can be seen as the probability of the sum of outcomes of what follows a bernoulli distribution, e.g. rolling a dice 30 times, what’s the probability that we get the outcome six? This count follows the binomial distribution, with parameter trials, and as success (a la Bernoulli);
-   *Poisson and Binomial*: like the binomial distribution, the poisson distribution is a distribution of a count — the number of times some event happened over a discrete time, given a rate for the event to ocur. It’s parametrized as (the and parameters of the binomial);
-   *Geometric and Negative Binomial*: while in the binomial we count the number of times the probability *succeeds* in yielding a given event after a number of trial, in the geometric distribution we count how many negative trials until we succeed in out event happening; The negative binomial distribution is a simple generalization of the geometric, measuring the number of failures until successes have occurred, not just 1;
-   *Exponential and Weibull*: the exponential distribution is the geometric on a continuous interval, parametrized by , like Poisson. While it will describes “time until event or failure” at a constant rate, the Weibull distribution models increases or decreases of rate of failures over time (i.e. models *time-to-failure*);
-   *Normal, Log-Normal, Student’s t, and Chi-squared*: if we take a set of values following the same (any) distribution and sum them, that sum of values follows approximatly the normal distribution — this is true regardless of the underlying distribution, and this phenomenon is called the [**Central Limit Theorem**](https://en.wikipedia.org/wiki/Central_limit_theorem). The log-normal distribution relates to distributions whose logarithm is normally distributed. The exponentiation of a normally distribution is log-normally distributed. Student’s t-distributions are normal distribution with a *fatter* tail, although is approaches normal distribution as the parameter increases. The chi-square distribution if the distribution of sum-of-squares of normally-distributed values;
-   *Gamma and Beta*: the gamma distribution is a generalization of the exponential and the chi-squared distributions. Like the exponential distribution, it is used to model waiting times e.g. the time until next events occur. It appears in machine learning as the conjugate prior to some distributions. The beta distribution is the conjugate prior to most of the other distributions mentioned here;

## Exponential Family of distributions

The exponential family of distribution is the set of distributions parametrized by that can be described in the form:

or in a more extensive notation:

where , , , and are known functions. An alternative notation to equation describes as a function of , regardless of the transformation from to . This new expression we call an exponential family in its **natural form**, and looks like:

The therm is a **sufficient statistic** of the distribution. The sufficient statistic is a function of the data that holds all information the data provides with regard to the unknown parameter values;

-   The intuitive notion of sufficiency is that is sufficient for , if there is no information in regarding beyond that in . That is, having observed , we can throw away for the purposes of inference with respect to ;
-   Moreover, this means that the likelihood *ratio* is the same for any two datasets and , i.e. if , then ;

The term is the **natural parameter**, and the set of values for which is finite is called the **natural parameter space** and is always convex;

The term is the **log-partition function** because it is the logarithm of a normalization factor, ensuring that the distribution sums up or integrates to one (without wich is not a probability distribution), ie.:

Another important point is that the mean and variance of can be derived by differentiating and computing the first- and second- derivative, respectively:

For the complete dataset )A(\\eta)$$ is equal to the mean of the sufficient statistic. We can now look at the second derivative:

and as expected the second derivative is equal to the variance of .

One requirement of the exponential family distributions is that the parameters *must* factorize (i.e. must be separable into products, each of which involves only one type of variable), as either the power or base of an enxponentiation operation. I.e. the factors must be one of the following:

where and are arbitrary functions of , and are arbitrary functions of ; and c is an arbitrary constant expression.

Another important point is that a product of two exponential-family distributions is as well part of the exponential family, but unnormalized:

Finally, the *exponential family distribution have conjugate priors* (i.e. prior and posterior distributions have distributions from the exponential family), and the *posterior predictive distribution has always a closed-form solution* (provided that the normalizing factor can also be stated in closed-form), both important properties for Bayesian statistics.

## Example: Univariate Gaussian distribution

The univariate Gaussian distribution is defined for an input as:

for a distribution with mean and standard deviation . By moving the terms around we get:

where:

-   ,
-   ,
-   ,
-   ,

We will now use the first and second derivative of to compute the mean and the variance of the sufficient statistic :

which is the mean of , the first component of the sufficient analysis. Takes the second derivative we get:

which is the standard deviation of our normal distribution, by definition.

## Example: Bernoulli distribution

Similarly, to compute the exponential family parameters in the Bernoulli distribution we follow as:

where:

-   ,
-   ,
-   ,
-   .

We now compute the mean of as:

which is the mean of a Bernoulli variable. Taking a second derivative yields:

which is the variance of a Bernoulli variable.

## Parameters for common distributions

The following table provides a summary of most common distributions in the exponential family and their exponential-family parameters. For a more exhaustive list, check the [Wikipedia entry for Exponential Family](https://en.wikipedia.org/wiki/Exponential_family).

Distribution

Probability Density/Mass Function

Natural parameter(s)

Inverse parameter mapping

Base measure

Sufficient statistic

Log-partition

Log-partition

[Bernoulli distribution](https://en.wikipedia.org/wiki/Bernoulli_distribution "wikilink")

([logit function](https://en.wikipedia.org/wiki/logit_function "wikilink"))

([logistic function](https://en.wikipedia.org/wiki/logistic_function "wikilink"))

[binomial distribution](https://en.wikipedia.org/wiki/binomial_distribution "wikilink")  
with known number of trials *n*

[Poisson distribution](https://en.wikipedia.org/wiki/Poisson_distribution "wikilink")

[negative binomial distribution](https://en.wikipedia.org/wiki/negative_binomial_distribution "wikilink")  
with known number of failures *r*

[exponential distribution](https://en.wikipedia.org/wiki/exponential_distribution "wikilink")

[Pareto distribution](https://en.wikipedia.org/wiki/Pareto_distribution "wikilink")  
with known minimum value

[Laplace distribution](https://en.wikipedia.org/wiki/Laplace_distribution "wikilink")  
with known mean *μ*

[normal distribution](https://en.wikipedia.org/wiki/normal_distribution "wikilink")  
known variance

[normal distribution](https://en.wikipedia.org/wiki/normal_distribution "wikilink")

[lognormal distribution](https://en.wikipedia.org/wiki/lognormal_distribution "wikilink")

[gamma distribution](https://en.wikipedia.org/wiki/gamma_distribution "wikilink")  
shape (10)α, rate (11)β

[gamma distribution](https://en.wikipedia.org/wiki/gamma_distribution "wikilink")  
shape (12)k, scale (13)θ

[beta distribution](https://en.wikipedia.org/wiki/beta_distribution "wikilink")

[multivariate normal distribution](https://en.wikipedia.org/wiki/multivariate_normal_distribution "wikilink")

[multinomial distribution](https://en.wikipedia.org/wiki/multinomial_distribution "wikilink")  
with known number of trials *n*

where

## Maximum Likelihood

On the [previous post](https://brunomaga.github.io/Bayesian-Linear-Regression), we have computed the Maximum Likelihood Estimator (MLE) for a Gaussian distribution. In thos post, we have seen that Gaussian — alongside plenty other distributions — belongs to the Exponential Family of Distributions. We will now show that the MLE estimator can be generalized across all distributions in the Exponential Family.

As in the Gaussian use case, to compute the MLE we start by applying the log-trick to the general expression of the exponential family, and obtain the following log-likelihood:

we then compute the derivative with respect to and set it to zero:

Not surprisingly, the results relates to the data only via the sufficient statistics , giving a meaning to our notion of sufficiency — *in order to estimate parameters we retain only the sufficient statistic*. For distributions in which , which include the the Bernoulli, Poisson and multinomial distributions, it shows that the sample mean is the maximum likelihood estimate of the mean. For the univariate Gaussian distribution, the sample mean is the maximum likelihood estimate of the mean and the sample variance is the maximum likelihood estimate of the variance.