### I used jython for an assignment as part of my OMSCS course in Machine Learning, covering topics in Machine Learning. 


------------


I modified some of the java files to compare different randomized optimization algorithms. Hopefully this could be useful if you do not want to use the defaults from Pushkar and want to play with some parameters.

Explicit instructions on usage: (Courtesy of my classmate Brian)


------------

- Install Java
- Download from: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
	- Pick the Java SE Development Kit 8u161 that matches your system.
	- JDK Installation Guide for Windows: https://docs.oracle.com/javase/8/docs/technotes/guides/install/windows_jdk_install.html#CHDEBCCJ
	- Add the needed Environment Variables (the source files from pushkar/ABAGAIL)
- Install ant
	-  Download from: http://ant.apache.org/bindownload.cgi
	- Pick the zip archive for 1.10.2
	- Install instructions here: http://ant.apache.org/manual/index.html
	- Add the needed Environment Variables (see item 6 below).
	- To get the library dependencies, I ran the optional
			ant -f fetch.xml -Ddest=system
- Download ABAGAIL source files from Git: from here: https://github.com/pushkar/ABAGAIL
	- Click Clone or download, and download the zip file.
	- Open the zip file and copy the ABAGAIL-master folder to a location of your choice (I chose Program Files to keep it close to the Java and apache-ant folders).
	- Make another copy of this folder named simply ABAGAIL (not strictly necessary, but I wanted a clean local copy just in case).
	- Change the permissions on the ABAGAIL folder to give full control to users of your system (or just yourself if you share your computer and have security concerns).
	- Right click - Properties -> Security tab -> Edit button.
- Open a command prompt
- Change directory to your ABAGAIL folder and run ant:
		cd "c:\Program Files\ABAGAIL"
		ant
	- This should create the ABAGAIL.jar file.
- Install jython
	- Download from: http://www.jython.org/downloads.html
	- Pick the Jython 2.7.0 installer.  After it downloads, just double click to run the installer.
	- Add the jython environment variable and path info 
	- System Environment Variables - final state:
		- ANT_HOME = C:\Program Files\apache-ant1.10.2
		- JAVA_HOME = C:\Program Files\Java\jdk1.8.0_161
		- JYTHON_HOME = C:\jython2.7.0
		- Path = whatever you started with plus the following 3 items appended to the end of the list:
			- C:\Program Files\Java\jdk1.8.0_161\bin
			- %ANT_HOME%\bin
			- %JYTHON_HOME%\bin
- To use ABAGAIL + jython from the command prompt:
- Navigate to the ABAGAIL\jython directory
- Run scripts with (example runs four peaks):
		jython -J-cp ../ABAGAIL.jar fourpeaks.py

- Install the Eclipse IDE from https://www.eclipse.org/getting_started/ and followed the "How to use ABAGAIL with Eclipse?" instructions in Git, and I use Sublime from https://www.sublimetext.com/ to work with python files.

Note: you may have to move this block to the beginning if your python doesn't execute

    from __future__ import



The differences I have specifically in my version are:
* the activation function from HyperbolicTangentSigmoid to LogisticSigmoid in BackPropogationNetworkFactory.java
* The learning rate to be .001 instead of .000001 in RROPUpdateRule.java
This was done to match the same hyperparameters when I did previous assignments using python/sklearn.


 



ABAGAIL
=======

[![Build Status](https://travis-ci.org/pushkar/ABAGAIL.svg?branch=master)](https://travis-ci.org/pushkar/ABAGAIL)

The library contains a number of interconnected Java packages that implement machine learning and artificial intelligence algorithms. These are artificial intelligence algorithms implemented for the kind of people that like to implement algorithms themselves.

Usage
------

* See [FAQ](https://github.com/pushkar/ABAGAIL/blob/master/faq.md)
* See [Wiki](https://github.com/pushkar/ABAGAIL/wiki)

Issues
-------

See [Issues page](https://github.com/pushkar/ABAGAIL/issues?state=open).

Contributing
------------

1. Fork it.
2. Create a branch (`git checkout -b my_branch`)
3. Commit your changes (`git commit -am "Awesome feature"`)
4. Push to the branch (`git push origin my_branch`)
5. Open a [Pull Request][1]
6. Enjoy a refreshing Diet Coke and wait 

Features
========

### Hidden Markov Models

* Baum-Welch reestimation algorithm, scaled forward-backward algorithm, Viterbi algorithm
* Support for Input-Output Hidden Markov Models
* Write your own output or transition probability distribution or use the provided distributions, including neural network based conditional probability distributions
* Neural Networks

### Feed-forward backpropagation neural networks of arbitrary topology
* Configurable error functions with sum of squares, weighted sum of squares
* Multiple activation functions with logistic sigmoid, linear, tanh, and soft max
* Choose your weight update rule with standard update rule, standard update rule with momentum, Quickprop, RPROP
* Online and batch training
* Support Vector Machines

### Fast training with the sequential minimal optimization algorithm
* Support for linear, polynomial, tanh, radial basis function kernels
* Decision Trees

### Information gain or GINI index split criteria
* Binary or all attribute value splitting
* Chi-square signifigance test pruning with configurable confidence levels
* Boosted decision stumps with AdaBoost
* K Nearest Neighbors

### Fast kd-tree implementation for instance based algorithms of all kinds
* KNN Classifier with weighted or non-weighted classification, customizable distance function
* Linear Algebra Algorithms

### Basic matrix and vector math, a variety of matrix decompositions based on the standard algorithms
* Solve square systems, upper triangular systems, lower triangular systems, least squares
* Singular Value Decomposition, QR Decomposition, LU Decomposition, Schur Decomposition, Symmetric Eigenvalue Decomposition, Cholesky Factorization
* Make your own matrix decomposition with the easy to use Householder Reflection and Givens Rotation classes
* Optimization Algorithms

### Randomized hill climbing, simulated annealing, genetic algorithms, and discrete dependency tree MIMIC
* Make your own crossover functions, mutation functions, neighbor functions, probability distributions, or use the provided ones.
* Optimize the weights of neural networks and solve travelling salesman problems
* Graph Algorithms

### Kruskals MST and DFS
* Clustering Algorithms

### EM with gaussian mixtures, K-means
* Data Preprocessing

### PCA, ICA, LDA, Randomized Projections
* Convert from continuous to discrete, discrete to binary
* Reinforcement Learning

### Value and policy iteration for Markov decision processes

[1]: https://help.github.com/articles/using-pull-requests
