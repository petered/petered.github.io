---
layout: default
title: Peter O'Connor's Research Site
---

I am trying to combine Spiking Neural Networks with Deep Learning.

The goal of this is to make Deep Learning applicable in more real-world situations, where you have many sensors and actuators running asynchronously.


### What's is Deep Learning? 

\(yes, I know, you know, but just for the sake of the narrative..\)

Deep learning has proved useful in solving many problems that can be phrased as function approximation.  

The approach is to state your problem such such that you have a parameterized, differentiable, scalar function $\mathcal L = f_\theta(\mathcal D)$, where $\mathcal D$ is your data and $\mathcal L$ becomes small when $f_\theta$ achieves some desired property.  Using the fact that $\mathcal L$ is differentiable with respect to $\theta$, we can iteratively adjust $\theta$ to minimize $\mathcal L$.  

For example in supervised learning, $\mathcal D = (x, y)$ and $\mathcal L = f_\theta(x, y) = \ell(g_\theta(x), y)$ so that $\mathcal L$ becomes small when $g_\theta$ gets good at predicting what y should be for a given x.  Most research in deep learning is either in figuring out a form of $f_\theta$ that works well for a given problem, or for a new problem, figuring out how to phrase it in the above form so that it can be solved by standard approaches.

It turns out that when $f_\theta$ is some variant on the theme of several layers of alternating linear operations and nonlinearities, you can solve a lot of tasks!

### What is *wrong* with deep learning?

In some situations, directly applying the standard approach as above can be horribly inefficient.  

For example, lets take a robot.

![](https://docs.google.com/drawings/d/e/2PACX-1vRIiayLadNEzjohN9D1n6i8PupdBdbpCTfHjIDDdiiB8HtYpq6lvGAoyOKcyUYecYXoJHAsGcrUZ2nW/pub?w=721&h=188)

There are several sensors, running at different rates, which we presumably want to combine into a unified latent representation which we can act upon.  

How shall we update our unified latent representation?

- If we update with the fast sensor (gyro) while holding the slow (camera) input fixed, we must recompute the latent representation with *almost* the same input many times.
- If we update with the slow sensor (camera) while processing the fast (gyro) in batches, we lose introduce all this latency into our response.

As another example, lets suppose we're extracting features from a video:

<iframe width="560" height="315" src="https://www.youtube.com/embed/1i9wgX_JN54" frameborder="0" allowfullscreen></iframe>

As neighbouring frames tend to be very similar, we end up doing *almost* the same computation repeatedly.

Wouldn't it be nice if there were a way to cache the current state at every layer of the network, so that the network only has to do a much smaller computation at each frame to update its state to accomodate the new changes?


### What is spiking, and how does it help?

Biological neurons live in a continuous time world of asynchronous sensory inputs.  Somehow, they manage to organize themselves into functional deep networks that update their state efficiently enough that running a network of about [86 billion neurons](https://en.wikipedia.org/wiki/List_of_animals_by_number_of_neurons#Whole_nervous_system) uses about [20W](https://hypertextbook.com/facts/2001/JacquelineLing.shtml).  

In the cortex, these neurons communicate with all-or-nothing impulses commonly called spikes.

There are many models of spiking neurons, but at the core they share two common principles that distinguish them from the type of neurons used in deep learning.
1) Neurons have an internal *state* that persists over time.
2) Neurons communicate with *spikes* - binary signals which are a function of integrated input over time.  

Suppose now that these spikes somehow encode the temporal change in a neuron's state.  If we say that computation happens every time a spike occurs, we can see that for static inputs the network should not compute.  In general the amount of computation should scale with the amount that is going on in the data, not simply the size of the network (as it does in most of deep learning).  

Now, since these neurons communicate with discrete signals, it is not obvious how to do gradient descent on such networks.  

To conclude, most of what I am working on is how to train networks of spiking neurons.  Our latest paper, [Temporally Efficient Deep Learning with Spikes](https://arxiv.org/abs/1706.04159) shows how this can be done effectively in the case of feedforward networks.  


<br><br><br>
