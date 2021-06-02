---
title: ":sparkles: Predicting Space Dust Densities"
layout: post
date: 2021-03-05 20:10
tag: 
- capstone
- random forest
- decision tree
#image: https://sergiokopplin.github.io/indigo/assets/images/jekyll-logo-light-solid.png
#headerImage: false
projects: true
hidden: false # count this post in blog pagination
description: "A captsone research project for my master's degree"
category: project
author: andrezazz
externalLink: false
---

For my master's degree at UVA, I got the chance to work on an incredible year-long capstone in collaboration with some fine folks at the Astronomy department. In essence, we wanted to build a better algorithm for predicting the density of dust in space that could form into planets. Our paper is available on arXiv [here](https://arxiv.org/abs/2104.12845).

Over the year, my collaborators and I tried a couple different approaches, focused around 2 in particular: mixture density networks (MDNs) and random forest regression (in that order). We tried the MDN thing for about 3 months, and there's a really great primer on MDNs on Towards Data Science [here](https://towardsdatascience.com/a-hitchhikers-guide-to-mixture-density-networks-76b435826cca). The big idea is leveraging an ensemble of neural networks to predict distributions, which seemed to be what we were going for. However, after a while, we couldn't get our accuracies to a high enough threshold, and we went our separate ways over the winter break, looking for new solutions.

Over the break, my teammates and I each stumbled upon a couple of crucial next steps: firstly, we needed to totally rethink how we measured the divergence between our true and predicted distributions (Kullback-Leibler divergence, while good, isn't symmetrized. So we switched to using [Jensen-Shannon divergence](https://medium.com/datalab-log/measuring-the-statistical-similarity-between-two-samples-using-jensen-shannon-and-kullback-leibler-8d05af514b15) and found it suited our purposes very well) , and we didn't need to dive into neural networks&mdash;a much simpler solution would actually give us much better results. And it was here that I learned a fundamental lesson: just because an approach is glitzy and cutting-edge and fancy, doesn't make it any better than something that you know works. Sometimes, a screwdriver is better than a power drill. And so we dove into random forest regression.

In the end, we were able to tune our regressor and make vast improvements in prediction time over the old algorithm, which is exactly what we'd set out to do. Together, we published a Python package, [astrodust](github.com/kehoffman3/astrodust) (which you can download [here](https://pypi.org/project/astrodust/)), and are looking to extend the project to predicting on one-dimensional evolutionary tracks of initial conditions, rather than fixed conditions.

---

What's inside?

- Jupyter Notebooks
- Python Scripts
- Package Development
- Links to Papers

---

[Check out our project site](https://andrezazz.github.io/dust-in-the-machine/) here.
