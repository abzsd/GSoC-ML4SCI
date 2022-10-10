# Quantum Generative Adversarial Networks for High Energy Physics Analysis at the LHC

![alt text](https://github.com/[username]/[reponame]/blob/[branch]/image.jpg?raw=true)

## What is a Generative Model?

- Generative models can generate new data instances.
- Discriminative models discriminate between different kinds of data instances.

Given a set of data instances X and a set of labels Y:

- Generative models capture the joint probability $p(X, Y)$, or just $p(X)$ if there are no labels.
- Discriminative models capture the conditional probability $p(Y | X)$.

A generative model includes the distribution of the data itself, and tells you how likely a given example is. For example, models that predict the next word in a sequence are typically generative models (usually much simpler than GANs) because they can assign a probability to a sequence of words.

A discriminative model ignores the question of whether a given instance is likely, and just tells you how likely a label is to apply to the instance.

Note that this is a very general definition. There are many kinds of generative model. GANs are just one kind of generative model.

## Generative Models are Hard
During the whole course of this project, I have learnt that developing GANs is in itself is a difficult task, namely because - 

A generative model for images might take into consideration correlations, which are very complicated distributions.

Whereas, the discriminative model is a basic classifier that learns to distinguish between two different images or probability distributions.

**INSERT IMAGE 1 HERE**


