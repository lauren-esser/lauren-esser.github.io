---
layout: post
title:      "From Neuron to Convolutional Neural Network"
date:       2020-10-28 16:55:11 -0400
permalink:  from_neuron_to_convolutional_neural_network
---

It's 2020 and so much has changed, while we aren't quite yet living like the Jetson's with our flying cars, alot of progress has been made. Look around you: from driverless cars, face recognition to unlock your smart phone, and automatic facebook tags. Image classification is in full use. We even use image classification to identify sicknesses such as pneumonia or cancer. How do computers do this? The answer lies in CNNs or Convolutional Neural Networks. 


### But before we being, lets talk about the human neuron....

<img src = 'http://ex-m.eu/wp/wp-content/uploads/2014/11/NEURON-CHAIN.jpg'>

Your crash course to human neurons is this: 

Neurons are specialized cells in your body that uses electrial impluses to send chemical signals from your brain to the rest of your body. They are the reason you can do pretty much anything. As shown in the image above, multiple neurons link together and these signals jump from one neuron to the next. Neurons have a part of them called the receptors. These receptors receive the information processes it and then send it on to the next neuron. This means that not necessarily each piece of information is moved forward, but simply the important messages that will have an impact on the body. (If you're interested look up inhibitors and excitatory neurotransmitters) So what does this have to do with convolutional neural networks?

### A LOT

Convolutional Neural Networks process pretty much the same was as the neurons in our brains. The neural networks are structured in different layers that receive an input. In the case of CNN's its an image. Each part of the image has a specfic weight, the higher the weight the strong that signal is and gets pushed through to the next layer. 



<img src = "https://miro.medium.com/max/1000/1*vkQ0hXDaQv57sALXAJquxA.jpeg">


Do you see how just with a neuron there is an input into the Convolutional Neural Network? In this case it is an image of a car. The second layer or "neuron" would be the convolution layer. Seen in the gif below this layer reads the image a section at a time (usually sized 3x3 or 5x5) and moves right until it completes the width of the image. It then moves down a row and completes the same process until the entire image is read. You may notice in the above image with the car that there is more than one convolution layer present. These layers operate similarly except that the earlier layer will capture low-level features like color, edges, and gradient orientation. As we move onto the next convolutional layer the details becomes more complex. There is potential for errors with convolutional layers including the image shrinking or the edges becoming less clear. To help fight against this the data scientist can use something called padding. Padding is basically adding a layer of pixels around the edge of the image in order to preserve the true size of the image when convolution is occurring. 

<img src = "https://miro.medium.com/max/1920/1*D6iRfzDkz-sEzyjYoVZ73w.gif">


Up next we can see the pooling layer. 



- down sample or reducing the spatial size of previous convolutional layers. By downsampling the convolutional layer it aids in decreasing the computational power required to execute the model. 
- Two types of pooling:
- Max pooling (most common) - takes a summary of the convolutions from a larger section of the original image. 
- Average pooling - returns the average of all values from the image. 
- Important hyperparameters: filter size and stride. 

<img src = "https://qph.fs.quoracdn.net/main-qimg-939c3123c48e27301f1a89c0a299dca8">

POOLING
ACTTIVATION
FLATTEN












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
https://towardsdatascience.com/a-comprehensive-guide-to-convolutional-neural-networks-the-eli5-way-3bd2b1164a53
https://learn.co/tracks/module-4-data-science-career-2-1/appendix/convolutional-neural-networks/convolutional-neural-networks
https://www.quora.com/What-is-max-pooling-in-convolutional-neural-networks








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
