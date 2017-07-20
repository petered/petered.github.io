---
layout: default
title: Peter O'Connor's Research Site
---

I am trying to combine Spiking Neural Networks with Deep Learning.

The goal of this is to make Deep Learning applicable in more real-world situations, where you have many sensors and actuators running asynchronously.


## What's wrong with Deep Learning?

Deep learning has proved useful in solving many problems that can be phrased as function approximation.  

The approach is to state your problem such such that you have a parameterized, differentiable, scalar function $\mathcal L = f_\theta(\mathcal D)$, where $\mathcal D$ is your data and $\mathcal L$ becomes small when $f_\theta$ achieves some desired property.  Using the fact that $\mathcal L$ is differentiable with respect to $\theta$, we can iteratively adjust $\theta$ to minimize $\mathcal L$.  

For example in supervised learning, $\mathcal D = (x, y)$ and $\mathcal L = f_\theta(x, y) = \ell(g_\theta(x), y)$ so that $\mathcal L$ becomes small when $g_\theta$ gets good at predicting what y should be for a given x.  Most research in deep learning is either in figuring out a form of $f_\theta$ that works well for a given problem, or for a new problem, figuring out how to phrase it in the above form so that it can be solved by standard approaches.

It turns out that when $f_\theta$ is some variant on the theme of several layers of alternating linear operations and nonlinearities, you can solve a lot of tasks!

**But...** sometimes it's not obvious how to apply the standard approach efficiently.  

For example, lets take a robot.

![](https://docs.google.com/drawings/d/e/2PACX-1vRIiayLadNEzjohN9D1n6i8PupdBdbpCTfHjIDDdiiB8HtYpq6lvGAoyOKcyUYecYXoJHAsGcrUZ2nW/pub?w=721&h=188)

There are several sensors, running at different rates, which we presumably want to combine into a unified latent representation which we can act upon.  


Page under construction... please come back later.
![](https://www.dhxsoftware.com/wp-content/uploads/construction-laws.jpg)





<br><br><br>



