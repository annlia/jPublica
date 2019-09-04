---
title       : Central limit theorem 
subtitle    : A practical introduction
author      : Giusi Moffa, PhD Statistics 
job         : Trial lecture, 11 October 2018
logo        : combinedlogostrans.png
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, selfcontained, draft}
lib_cdn: "https://cdn.rawgit.com/ramnathv/slidifyLibraries/master/inst/libraries"

--- &jtwocol w1:58% w2:38%



<!-- It seems caching happens by default, and caching of the options chunk appears to break things down -->



## Normal distribution



*** =left

Continuous random variable $X$ with normal distribution

* probability density function

$$f(x; \mu, \sigma) = \frac{1}{\sigma \sqrt{2 \pi}} e^{ -\frac{1}{2} \left( \frac{x-\mu}{\sigma} \right)^2 }$$

$x \in \mathbb{R}, \mu \in \mathbb{R}, \sigma \in \mathbb{R}_+$

* mean $\mathbb{E}(X)=\mu$, variance $\mathbb{V}ar(X)=\sigma^2$

$$X \thicksim \mathcal{N}(\mu, \sigma^2)$$

* cumulative distribution function

$$F(x) = \Phi\left(\frac{X-\mu}{\sigma}\right), \Phi(z) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^z e^{-\frac{t^2}{2}}\mathrm{d}t $$

*** =right

![plot of chunk normalPlots](assets/fig/normalPlots-1.png)![plot of chunk normalPlots](assets/fig/normalPlots-2.png)

--- &jtwocol w1:42% w2:54%

## Sum of normal random variables

*** =left 

If $X_1, X_2, \ldots , X_n$ are mutually independent normal random variables with means $\mu_1, \mu_2, \ldots , \mu_n$ and variances $\sigma_1^2, \sigma_2^2, \ldots, \sigma_n^2$

then the linear combination:

$$Y = \sum_{i=1}^n c_i X_i$$
follows a normal distribution 
$$Y \thicksim \mathcal{N}\left(\sum_{i=1}^n c_i \mu_i, \sum_{i=1}^n c_i^2 \sigma_i^2\right)$$
*** =right

![plot of chunk sumNormal](assets/fig/sumNormal-1.png)

$$X_1 \thicksim \mathcal{N}(2,1)$$ 
$$X_2 \thicksim \mathcal{N}(5,2)$$
$$X_1 + X_2 \thicksim \mathcal{N}(7,3)$$

--- &jtwocol w1:42% w2:54%

## Sampling distribution of the sample mean

*** =left

</br></br>
If $X_1, X_2, \ldots X_n$ are a random sample of size $n$ from a normal $\mathcal{N}(\mu, \sigma^2)$ population with mean $\mu$ and variance $\sigma^2$, then the sample mean:
  
$$\bar{X} = \frac{X_1 + X_2 + \dots + X_n}{n}$$

follows a normal distribution with mean $\mu$ and variance $\sigma^2/n$

$$\bar{X} \thicksim \mathcal{N}\left(\mu, \frac{\sigma^2}{n}\right)$$

*** =right

</br></br></br>
![plot of chunk normalSampleMean](assets/fig/normalSampleMean-1.png)

--- &jtwocol w1:58% w2:38%

## Uniform distribution - sample mean

*** =left

Continuous random variable $X$ with uniform distribution

* probability density function

$$f(x; a, b) = \left \{ \begin{array}{cc} \frac{1}{b-a} & \ a \le x \le b  \\
0 & \mathrm{otherwise}
\end{array} \right.$$

* mean $\mathbb{E}(X)=\frac{1}{a+b}$, variance $\mathbb{V}ar(X)=\frac{1}{12}(b-a)^2$

$$X \thicksim U(a, b)$$

* cumulative distribution function

$$F(x; a, b) = \left \{ \begin{array}{cc} 0 & x < a  \\
\frac{x-a}{b-a} & a \le x < b \\
1 & x \ge 1
\end{array} \right.$$

*** =right

![plot of chunk simUnif](assets/fig/simUnif-1.png)
<img src="gifAnimation/runif30.gif" width="350px">

--- &jtwocol w1:58% w2:38%

## Exponential distribution - sample mean

*** =left

Continuous random variable $X$ with exponential distribution

* probability density function

$$f(x; \lambda) = \left \{ \begin{array}{cc} \lambda e^{-\lambda x} & x \ge 0  \\
0 & x < 0 
\end{array} \right.$$

* mean $\mathbb{E}(X)=\frac{1}{\lambda}$, variance $\mathbb{V}ar(X)=\frac{1}{\lambda^2}$

$$X \thicksim \mathrm{Exp}(\lambda)$$

* cumulative distribution function

$$F(x; \lambda) = \left \{ \begin{array}{cc} 1 - e^{-\lambda x} & x \ge 0  \\
0 & x < 0 
\end{array} \right.$$

*** =right

![plot of chunk simExp](assets/fig/simExp-1.png)
<img src="gifAnimation/rexp30.gif" width="350px">

--- &jtwocol w1:58% w2:38%

## Poisson distribution - sample mean

*** =left

Discrete random variable $X$ with Poisson distribution

* probability mass function

$$f(k; \lambda) = \frac{\lambda^k e^-\lambda}{k!} \qquad  k=0, 1, 2, \ldots$$

* mean $\mathbb{E}(X)=\lambda$, variance $\mathbb{V}ar(X)=\lambda$

$$X \thicksim \mathrm{Pois}(\lambda)$$

* cumulative distribution function

$$F(x; \lambda) = \left \{ 
\begin{array}{cc}
\frac{\Gamma(\lfloor k+1 \rfloor, \lambda)}{\lfloor k \rfloor !} & k \ge 0 \\
0 & k <0
\end{array}
\right.$$

*** =right

![plot of chunk simPoisson](assets/fig/simPoisson-1.png)
<img src="gifAnimation/rpois30.gif" width="350px">

--- &jtwocol w1:58% w2:38%

## Bernoulli distribution - sample mean

*** =left

Binary random variable $X$: Bernoulli distribution

* probability mass function

$$f(k;p) = p^k(1-p)^{k-1} \qquad k \in {0,1}$$

* mean $\mathbb{E}(X)=p$, variance $\mathbb{V}ar(X)=p(1-p)$

$$X \thicksim \mathcal{B}(1,p)$$

* cumulative distribution function

$$F(x) = \left \{ \begin{array}{cc} 0 & k < 0  \\
1-p & 0 \le k < 1 \\
1 & k \ge 1
\end{array} \right.$$

*** =right

![plot of chunk simBernoulli](assets/fig/simBernoulli-1.png)
<img src="gifAnimation/rbinom30.gif" width="350px">

---

## Classical - Central limit theorem

**Fundamental theorem in statistics**

Let $X_1, X_2, \ldots X_n$ be a sequence of $n$ indipendent identically distributed random variables, from __any__ distribution with 

* (finite) mean $\mathbb{E}(X_i) = \mu$ 
* (finite) variance $\mathbb{V}ar(X_i) = \mathbb{E}(X_i -\mu)^2 = \sigma^2$.  

For large $n$ the sample mean $\bar{X} = \frac{X_1 + X_2 + \dots + X_n}{n}$ follows an approximate normal distribution with

* mean $\mathbb{E}(\bar{X}) = \mu$, variance $\mathbb{V}ar(\bar{X}) = \sigma_{\bar{X}}^2 = \frac{\sigma^2}{n}$

$$\bar{X} \xrightarrow[]{\; d \;} \mathcal{N}\left(\mu, \frac{\sigma^2}{n}\right), \quad Z_n =\frac{\bar{X} - \mu}{\sigma/\sqrt{n}} \xrightarrow[]{\; d \;} \mathcal{N}\left(0, 1\right)$$

The sampling distribution of the sample mean is approximately normal regardless of the distribution of the underlying sample.

---

## Central limit theorem - sketch of proof

We can write $Z_n = \sum_{i=1}^n \frac{X_i - \mu}{\sigma \sqrt{n}} = \sum_{i=1}^n \frac{Y_i}{\sqrt{n}}$, with $Y_i = \frac{X_i - \mu}{\sigma}$

By the properties of the characteristic function, defined as $\varphi_X(t) = \mathbb{E}(e^{-itX})$ for a random variable $X$, and given that $Y_i$'s are iid, we get the following for $Z_n$

$$\varphi_{Z_n}(t) = \left[ \varphi_{Y_1} \left( \frac{t}{\sqrt{n}} \right) \right]^n$$
By Taylor's theorem: $\varphi_{Y_1}(t/\sqrt{n}) = 1-\frac{\sigma^2}{2}t^2 + O(t^3)$, 
so that

$$\varphi_{Z_n}(t) = \left( 1-\frac{\sigma^2}{2}t^2 + O(t^3) \right)^n \longrightarrow e^{-\frac{1}{2}t^2}, \quad n \rightarrow \infty$$
characteristic function of a standard normal r.v., with Levy's continuity theorem to bridge pointwise convergence of the characteristic function to convergence in distribution and complete the proof.

Lyapunov extension to unequal means and variances:  
$\frac{1}{s_n} \sum_{i=1}^n (X_i-\mu_i) \xrightarrow[]{\; d \; } \mathcal{N}(0,1)$,
with $s_n^2 = \sum_{i=1}^n \sigma_i^2$

--- &twocol

## Cauchy distribution

*** =left

Continuous random variable $X$ with Cauchy distribution

* probability density function

$$f(x; x_0, \gamma) = \frac{1}{\pi\gamma \left[ 1 + \left( \frac{x-x_0}{\gamma} \right)^2 \right]}$$

* with location $x_0$, scale $\gamma>0$, mean and variance **undefined**

$$X \thicksim \mathrm{Cauchy}(x_0, \gamma)$$

* cumulative distribution function

$$F(x; x_0, \gamma) = \frac{1}{\pi}\arctan\left( \frac{x-x_0}{\gamma} \right) + \frac{1}{2}$$

*** =right

![plot of chunk simCauchy](assets/fig/simCauchy-1.png)

--- &jtwocol w1:48% w2:48%

## The Quincunx

*** =left
Example of a Galton board/box or quincunx

<img src="figs/quincunx_figure_zoom.png" alt="" height=360px> &nbsp; <img src="figs/quincunx.jpg" alt="" height=360px>

* Sir Francis Galton (1893)
* physical demonstration of the CLT

*** =right
<img src="figs/galton-board-large_1_mobile_1.gif", loop="-1"><br>
[http://galtonboard.com/]


<!-- _Quincunx is a good scrabble word!  Galton along with being the half-cousin of Darwin was also the "father" of eugenics!_ -->

--- &twocol

## Historical notes

*** =left

* 1733: early version, for binomial distribution with $p=1/2$, by Abraham de Moivre  
(44 years before Gauss' birth)
* 1812: extended by Pierre-Simon Laplace
* 1920: named __Central Limit Theorem__ by George Pólya

*** =right 

![](figs/AdamsCLT.jpg)

<!-- Inspired by https://www.johndcook.com/blog/2010/01/05/how-the-central-limit-theorem-began/ -->

---

## References

Course from Penn State
https://onlinecourses.science.psu.edu/stat414/node/176/

https://www.johndcook.com/blog/central_limit_theorems/
https://www.johndcook.com/blog/2010/01/05/how-the-central-limit-theorem-began/

Animate a Monte Carlo simulation
https://roh.engineering/post/animating-a-monte-carlo-simulation/

https://freakonometrics.hypotheses.org/52347

https://www.learner.org/courses/mathilluminated/units/7/textbook/06.php

http://www.sthda.com/english/wiki/ggplot2-histogram-plot-quick-start-guide-r-software-and-data-visualization

https://www.wikiwand.com/en/De_Moivre%E2%80%93Laplace_theorem

<style>

.title-slide {
  background-color: #FFFFFF;
}

.title-slide hgroup > h1{
font-size: 180% ;
}

.title-slide hgroup > h1, 
.title-slide hgroup > h2 {
  color: #005579 ; /* novartis blue, #116BB1 eth blue, #EF5150 default*/
}

slide.segue h2 {
  color: #005579 ; /* novartis blue, #116BB1 eth blue, #EF5150 default*/
}

slide:not(.segue) h2 {
  color: #005579 ; /* novartis blue, #116BB1 eth blue, #EF5150 default*/
}

/* Styles for Title Slide */
.title-slide hgroup > h1{
  font-family: "Open Sans Condensed", 'Garamond', 'Calibri', sans-serif;
  font-weight: 700;
}

.title-slide hgroup > h2{
  font-family: "Open Sans Condensed", 'Garamond','Calibri', sans-serif;
  font-weight: 700;
  font-size: 150% ;
}

slide p {
 font-family: 'Open Sans','Helvetica', 'Crimson Text', 'Garamond',  'Palatino', sans-serif;
 color: #444444 ;
 font-size: 80%
} 

footer p {
 font-family: 'Open Sans','Helvetica', 'Crimson Text', 'Garamond',  'Palatino', sans-serif;
 color: #444444 ;
} 

p.cite {
  color: #005579 ; /* novartis blue, #116BB1 eth blue, #EF5150 default*/
  font-size: 67% ;
}

em {
  color: #005579 ; /* novartis blue, #116BB1 eth blue, #EF5150 default*/
  font-size: 67% ;
  /*font-style: italic*/
}

strong {
  color: #005579 ; /* novartis blue, #116BB1 eth blue, #EF5150 default*/
  /*font-size: 67% */;
  font-weight: bold;
}

mark {
  background-color:transparent;
  color: #888888 ;
  font-size: 67% ;
  /*font-style: italic*/
}

/* Fonts and Spacing */
article p, article li, article li.build, section p, section li{
  text-align: left;
}

footnote {
  position: absolute;
  bottom: 0;
  margin-bottom: 10px;
  width: 80%;
  font-size: 67%;
  line-height: 1.5;
}

table th {
  background: #99bbc9;
  color: #005579;
  text-transform: uppercase;
}
table td {
  border-bottom: 1px solid #CFCEBD;
}
table tr:nth-child(2n) {
  background: #d6e3e9;
}
table tr:nth-child(2n+1) {
  background: #ffffff;
}

#hidestuff {margin-top:-124px;}
#hidestuffless {margin-top:-100px;}
#hidestuffevenless {margin-top:-75px;}
#hidestuffpic {margin-top:-200px;}
#hidestuffbigpic {margin-top:-250px;}

#testfooter {
  font-size: 12pt;
  position: absolute;
  bottom: 20px;
  right: 60px;
  line-height: 1.9;
}

#testfooter:after {
   content: "/10";
}

/* change logo size */
aside.gdbar img {
  width: 504px; 
  height: 68px; 
  position: absolute;
  right: 0;
  margin: 15px 15px;
}

/* change logo background */
aside.gdbar {
  height: 100px;
  width: 281px;
  position: absolute;
  left: 10px;
  top: 125px;
}

aside.gdbar {
  width: 534px; 
}

/* Reduce Space between Title and Body */
slides > slide > hgroup + article {
  margin-top: 30px;
}

slides > slide:not(.nobackground):after {
  font-size: 12pt;
  content: "";
  position: absolute;
  bottom: 20px;
  right: 60px;
  line-height: 1.9;
}

</style>
