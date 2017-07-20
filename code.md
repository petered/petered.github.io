---
layout: default
title: Code
---


# Artemis
Artemis aims to get rid of all the boring, bureaucratic coding (plotting, file management, organizing experiments, etc) involved in machine learning projects, so you can get to the good stuff quickly.  Get it at [https://github.com/QUVA-Lab/artemis](https://github.com/QUVA-Lab/artemis)

# Plato
I made a nice deep learning library called Plato.  It's built on top of Theano.  Nobody uses it except me.  But you should use it, because it's really nice.  You can get it at [https://github.com/petered/plato](https://github.com/petered/plato).  A tutorial explaining what it is is [here](https://rawgit.com/petered/plato/master/plato_tutorial.html).

# Public-Release
A small utility for exporting a script, along with all its dependencies, into a new GitHub repository
https://github.com/petered/public-release

# Spiking MLP
If you want to replicate the experiments in our recent paper, [Deep Spiking Networks](http://arxiv.org/abs/1602.08323).
https://github.com/petered/spiking-mlp.

# DeepSpike
The Spiking MLP code relies on our Java library for running spiking neural networks.  That's called DeepSpike, and you can get it at [https://github.com/petered/DeepSpike](https://github.com/petered/DeepSpike).  I wrote it in Java because it would run too slowly in Python, and our spiking networks can't just be vectorized into numpy expressions.

# JSpikeStack
Way back for my masters project I made another java spiking network library called JSpikeStack.  It runs a pre-trained network of LIF Neurons as a Deep Belief Network.  You can find out more about that at [https://sites.google.com/site/thebrainbells/home/jspikestack](https://sites.google.com/site/thebrainbells/home/jspikestack).
