---
layout: post
title:      "From Neuron to Convolutional Neural Network"
date:       2020-10-28 20:55:10 +0000
permalink:  from_neuron_to_convolutional_neural_network
---

It's 2020 and so much has changed, while we aren't quite yet living like the Jetson's with our flying cars, alot of progress has been made. Look around you: from driverless cars, face recognition to unlock your smart phone, and automatic facebook tags. Image classification is in full use. We even use image classification to identify sicknesses such as pneumonia or cancer. How do computers do this? The answer lies in CNNs or Convolutional Neural Networks. 

But before we being, lets talk about the human neuron....

<img src = 'http://ex-m.eu/wp/wp-content/uploads/2014/11/NEURON-CHAIN.jpg'>

Your crash course to human neurons is this: Neurons are specialized cells in your body that uses electrial impluses to send chemical signals from your brain to the rest of your body. They are the reason you can do pretty much anything. As shown in the image above, multiple neurons link together and these signals jump from one neuron to the next. Neurons have a part of them called the receptors. These receptors receive the information processes it and then send it on to the next neuron. This means that not necessarily each piece of information is moved forward, but simply the important messages that will have an impact on the body. (If you're interested look up inhibitors and excitatory neurotransmitters) So what does this have to do with convolutional neural networks?

## A LOT

Convolutional Neural Networks process pretty much the same was as the neurons in our brains. The neural networks are structured in different layers that receive an input. In the case of CNN's its usually an image. Each part of the image has a specfic weight, the higher the weight the strong that signal is and gets pushed through to the next layer. 


maybe neuron sends messages from the eyes to the brian to recognize differences between faces. After years of training it can now recognize differences in each face you come across to know the difference between Adam and Derek. 




How a CNN does it:

Boat image explaination here and gif?

Step one: Upload Image
Step two: Perform Convolution
Step three: Apply a pooling layer
Step four: Add another convolution operation activation function
Step five: Apply a pooling lyaer
Step six: Flatting the last layer output into a linear vector.
Step seven: Pass linear vector into neural network
Step eight: Final layer provides a probability for each class





Sources: 
https://medium.com/towards-artificial-intelligence/convolutional-neural-networks-for-dummies-afd7166cd9e









Thoughts for writing:
- A Neural Network is a web of interconnected entities known as nodes wherein each node is responsible for a simple computation. In this way, a Neural Network functions similarly to the neurons in the human brain. 
- One of the most popullar algorithms in ML
- Picture of input output of a neuron and a step by step


What do neural networks do?


What is it?
A neural network consist of nodes and connections between notes. 
Has parameters that fit into to data.
starts out with unknown parameter values, (backpropagation estimates parameters)
Can discuss activation functions = sigmoid, relu, softplus, etc
discuss hidden layers and how many nodes go into each hidden layer
