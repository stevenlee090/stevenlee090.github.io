---
title: "Transition from KaTeX to MathJax"
layout: post
date: 2018-03-20 08:56
image: # /assets/images/iterm.png
headerImage: false
tag:
- mathjax
- katex
- math
- typeset
star: false
category: blog
author: stevenlee
description: Moving from KaTeX to MathJax for mathematics typeset.
---

After numerous unsuccessful attempts to solve the KaTeX related issues, I eventually decided to try out MathJax and see how that would work for me.

MathJax turns out to be quite easy to setup, once you know where to place the code snippet. However, I was hung up for a while because I did not realise that I was using `http` instead of `https` for the MathJax code snippet, and for that reason, the web page was unable to render itself properly when all the changes are pushed onto GitHub. The underlying reason is because GitHub pages are using `https` protocol by default and it would not load the `http` code snippet due to the lower level of security.

Moreover, all the features work as expected and I was able to produce the desired outputs including matrices and display mode equations.

## MathJax Setup for Jekyll

1. From the official Jekyll documentation's [Math Support Section](https://jekyllrb.com/docs/extras/), we can see the snippet required:
```
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
```
2. Add the code snippet above to `page.html` which should be under `_layouts` folder. This particular step could vary slightly depending on the existing Jekyll theme and its folders' setup.

3. Try to write some math equation(s) and see if they render properly. For example, the Lorentz equations shown in the next section can be generated with the code shown below:
```
\\[
    \begin{aligned}
    \dot{x} & = \sigma(y-x) \\\
    \dot{y} & = \rho x - y - xz \\\
    \dot{z} & = -\beta z + xy
    \end{aligned}
\\]
```

---

## Examples by using MathJax

Here I have some examples taken from the MathJax [Demo Page](http://www.mathjax.org/demos/tex-samples/).

#### The Lorentz Equations

\\[
    \begin{aligned}
    \dot{x} & = \sigma(y-x) \\\
    \dot{y} & = \rho x - y - xz \\\
    \dot{z} & = -\beta z + xy
    \end{aligned}
\\]

#### The Cauchy-Schwarz Inequality

$$ \left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right) $$

#### A Cross Product Formula

\\[\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0
\end{vmatrix} \\]

#### The probability of getting \\(k\\) heads when flipping \\(n\\) coins is

$$ P(E) = {n \choose k} p^k (1-p)^{ n-k} $$

#### An Identity of Ramanujan

\\[ \frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} =
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}}
{1+\frac{e^{-8\pi}} {1+\ldots} } } } \\]

#### A Rogers-Ramanujan Identity

\\[  1 +  \frac{q^2}{(1-q)}+\frac{q^6}{(1-q)(1-q^2)}+\cdots =
\prod_{j=0}^{\infty}\frac{1}{(1-q^{5j+2})(1-q^{5j+3})},
\quad\quad \text{for $|q|<1$}. \\]


#### Maxwell's Equations

\\[  \begin{aligned}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} & = \frac{4\pi}{c}\vec{\mathbf{j}} \\\   \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\\
\nabla \cdot \vec{\mathbf{B}} & = 0 \end{aligned}
\\]
