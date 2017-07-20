---
layout: default
title: Peter O'Connor's Research Site
---

Deep learning has proved useful in solving many problems that can be phrased as function approximation.  

The approach is to state your problem such such that you have a parameterized, differentiable, scalar function $\mathcal L = f_\theta(\mathcal D)$, where $\mathcal D$ is your data and $\mathcal L$ becomes small when $f_\theta$ achieves some desired property.  Using the fact that $\mathcal L$ is differentiable with respect to $\theta$, we can iteratively adjust $\theta$ to minimize $\mathcal L$.

For example in supervised learning, $\mathcal D = (x, y)$ and $\mathcal L = f_\theta(x, y) = \ell(g_theta(x), y)$ so that $\mathcal L$ becomes small when $g_\theta$ gets good at predicting what y should be for a given x.  Most research in deep learning is either in figuring out a form of $f_\theta$ that works well for a given problem, or for a new problem, figuring out how to phrase it in the above form so that it can be solved by standard approaches.






<br><br><br>



