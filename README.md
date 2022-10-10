# Quantum Generative Adversarial Networks for High Energy Physics Analysis at the LHC

![logo](https://github.com/abzsd/GSoC-ML4SCI/blob/main/data/logo.jpeg?raw=true)
This project is an official submission to the [Google Summer of Code 2022](https://summerofcode.withgoogle.com/) program carried out under the supervision of mentors from the ML4SCI organization.
The official project webpage can be found [here](https://summerofcode.withgoogle.com/programs/2022/projects/QzBcIxrS).

## Setup

It is preferable to set up a virtual environment so that you do not face any package version conflicts.
```shell
python -m venv env_name
cd env_name
.\Scripts\activate
```

Clone the repository and navigate to the required folder.
```shell
git clone https://github.com/abzsd/GSoC-ML4SCI
```
Navigate to the folder
```shell
cd GSoC-ML4SCI
```
Install the necessary libraries and frameworks.
```shell
pip install -r requirements.txt
```

_Note: If the code does not run or gives errors, try using google colab and using the following versions for tf and tfq.
<br>
tensorflow==2.7.0
<br>
tensorflow-quantum==0.6.0 --use-deprecated=legacy-resolver_
***

##Project Overview
One of the challenges in High-Energy Physics(HEP) is fast simulation of particle transport, and hence various deep neural network methods have been studied for reducing the time-consumption. The Generative Adversarial Networks(GANs) have achieved similar performance as the full Monte Carlo based simulation, but with reduced time taken. As quantum computers promise many advantages over classical computing, comes a question on whether quantum machine learning (QML) can give any improvement in solving the problem. This project aims to demonstrate quantum machine learning's potential, specifically Quantum Generative Adversarial Network (QGAN), in HEP events data generation and classification from image data. Although many previous works have tried to classify images with QGAN, none of them is fully quantum. This project will be aimed at producing new 'accurate' data with a fully quantum implementation of QGAN, along with integrating it with the Physics channel of the LHC e.g. the Higgs-Boson production event.

##Datasets
- Photon-Electron Electromagnetic Calorimeter (ECAL) Dataset
- Jet Mass Image Dataset
- Quark-Gluon Dataset

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


![logo](https://github.com/abzsd/GSoC-ML4SCI/blob/main/data/logo1.svg?raw=true)

## Models
### Hybrid Quantum GAN
This model of GAN can either have a quantum/classical generator, and a quantum/classical discriminator. The generator and the discriminator have convolutional layers either quantum or classical. 

### Fully Quantum GANs
This model will have both generator and discriminator as quantum convolutional layers. 

### Entangled Quantum GAN
This approach is inspired by this [paper](https://arxiv.org/abs/2105.00080) in which a fidelity test is used. A [Swap test](https://en.wikipedia.org/wiki/Swap_test)(fidelity test) is a quantum computation technique through which we can measure the closeness of two states, i.e., how much two quantum states are similar to each other. The other uniqueness of this approach is that we upload the random data and the real data both at the same time in one train step instead of one following the other.

 There is also an implementation of the fully quantum model using pennylane library, and also some notebooks containing the demo notebooks for the implementation of ```lightning.qubit``` and ```lightning.gpu```, which uses ```cuQuantum-SDK``` by NVIDIA.
 
 ## Results
 The training for GANs is a difficult task even for classical ML programs, and the addition of quantum computing (provided its nascent status) makes it more difficult. The unavailability of large quantum systems, is hence mitigated by the use of simulators, like those given by Pennylane and NVIDIA. As the number of instances increase, the amount of time required to compile and execute the entire circuit also increases. Hence, as you would be able to see in this project that, there were instances where we had to reduce the dimensionality and amount of data, in accordance with the limitations imposed by the early stage devices/simulators. 
 Some of the results that I had obtained during the course of my training are displayed below - 

![logo](https://github.com/abzsd/GSoC-ML4SCI/blob/main/plots/dcgan.gif?raw=true)

![logo](https://github.com/abzsd/GSoC-ML4SCI/blob/main/plots/dcgan_v2.gif?raw=true)

![logo](https://github.com/abzsd/GSoC-ML4SCI/blob/main/plots/dcgan_v3.gif?raw=true)

![logo](https://github.com/abzsd/GSoC-ML4SCI/blob/main/plots/QDiscriminator_v2_loss.png?raw=true)
