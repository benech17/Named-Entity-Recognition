Named Entity Recognition
==========================

I made my first artificial neural network to find if a sentence (in French) contains a Named Entity (person,place,organization) or not. 

I learned the fundamentals of Machine Learning in python with the O'Reilly book [Hands-on Machine Learning with Scikit-Learn and TensorFlow](https://www.lpsm.paris/pageperso/has/source/Hand-on-ML.pdf):

[![book](http://akamaicovers.oreilly.com/images/0636920052289/cat.gif)](https://www.lpsm.paris/pageperso/has/source/Hand-on-ML.pdf)


# Installation
If you are familiar with Python and you know how to install Python libraries, go ahead and install the libraries listed in `requirements.txt` and jump to the [Starting Jupyter](#starting-jupyter) section. If you need detailed instructions, please read on.

## Python & Required Libraries
Of course, you obviously need Python. You should prefer the Python 3.6.X version.
On Linux, unless you know what you are doing, you should use your system's packaging system. For example, on Debian or Ubuntu, type:

    $ sudo apt-get update
    $ sudo apt-get install python3

## Using pip 
you need to install several scientific Python libraries that are necessary for this project, in particular NumPy, Matplotlib, Pandas, Jupyter and TensorFlow (and a few others). For this, you can either use Python's integrated packaging system, pip, or you may prefer to use your system's own packaging system (if available, e.g. on Linux, or on MacOSX when using MacPorts or Homebrew). The advantage of using pip is that it is easy to create multiple isolated Python environments with different libraries and different library versions (e.g. one environment for each project). The advantage of using your system's packaging system is that there is less risk of having conflicts between your Python libraries and your system's other packages. Since I have many projects with different library requirements, I prefer to use pip with isolated environments. 

These are the commands you need to type in a terminal if you want to use pip to install the required libraries.
First you need to make sure you have the latest version of pip installed:

    $ pip3 install --user --upgrade pip

The `--user` option will install the latest version of pip only for the current user. If you prefer to install it system wide (i.e. for all users), you must have administrator rights (e.g. use `sudo pip3` instead of `pip3` on Linux), and you should remove the `--user` option. The same is true of the command below that uses the `--user` option.

Next, you can optionally create an isolated environment. This is recommended as it makes it possible to have a different environment for each project (e.g. one for this project), with potentially very different libraries, and different versions:

    $ pip3 install --user --upgrade virtualenv
    $ virtualenv -p `which python3` env

This creates a new directory called `env` in the current directory, containing an isolated Python environment based on Python 3. If you installed multiple versions of Python 3 on your system, you can replace `` `which python3` `` with the path to the Python executable you prefer to use.

Now you must activate this environment. You will need to run this command every time you want to use this environment.

    $ source ./env/bin/activate

Next, use pip to install the required python packages. If you are not using virtualenv, you should add the `--user` option.

    $ pip3 install --upgrade -r requirements.txt

Great! You're all set, you just need to start Jupyter now.

## Starting Jupyter
Okay! You can now start Jupyter, simply type:

    $ jupyter notebook

This should open up your browser, and you should see Jupyter's tree view, with the contents of the current directory. If your browser does not open automatically, visit [127.0.0.1:8888](http://127.0.0.1:8888/tree). Click on `index.ipynb` to get started!

# How to Use 
there are 5 files that differ in the way of collecting data in order to feed the Artificial Neural Network.
* Balanced_1293_91%.ipynb : the data is from a dataset of 1293 sentences and was balanced, 91% accuracy score.
* Balanced_671_88%.ipynb : the data is from a dataset of 671 sentences and was balanced, 88% accuracy score.
* ImBalanced_1293_87%.ipynb :  the data is from a dataset of 1293 sentences, 87% accuracy score.
* ImBalanced_671_87%.ipynb :  the data is from a dataset of 671 sentences, 87% accuracy score.
* Position_1293_Balanced_97%.ipynb : the position of each word is also a parameter.

## To Sum up 
To create my first artificial neural network, I needed Data so I have made some pre-work as I found a way to collect sentences from newspapers articles and analyze it ( number of words,quotes,uppercase ...) as parameters.
Once this Database (managed with phpmyadmin) created and completed, I used the StanfordPostagger library to tag each word from each sentences and then, I could use Tensorflow and Scikit-Learn to make my first artificial neural network.
The way to implement a sentence into an input vectorn the number of neurons in each layers and the number of hidden Layers were central issues that I could get through thanks to the time I spend reading and understanding each part of this book.
The artificial neural network was made to find if a sentence (in French) contains a Named-Entity or not.The named-entity could be a person,a place or an organization.
As a result, I tested the accuracy score with 3 tests: 
* [the F1 score](https://en.wikipedia.org/wiki/F1_score) 
* [the Matthews_correlation_coefficient](https://en.wikipedia.org/wiki/Matthews_correlation_coefficient)
* [Simple accuracy score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html)


and the model who take as additional parameter the position of each word in a sentence had 97% accuracy score.
