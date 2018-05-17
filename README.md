# Basic Tutorial: Guess the Correlation Game
[Empirica](https://empirica.ly/) is an open-source JavaScript framework for running multiplayer interactive experiments and games in the browser.This tutorial walks you through building a simple, but fully functional experiment that demonstrates many of the core features of Empirica. 

This will guide you step by step, from install and run a local instance to deploy and test your first Empirica experiment in real world. For the purposes of this tutorial, we will build a multiplayer and interactive 'Guess the Correlation' game. This is similar to the experiment we used for our paper: [The Wisdom of the Network: How Adaptive Networks Promote Collective Intelligence][1]
 
 [1]: https://arxiv.org/abs/1805.04766

The intended audience for this tutorial is someone who:

1. **Is familiar with experiment design** and understanding what we mean by random assignment, treatments, independent variables.

2. **Knows the basics of the JavaScript and [React](https://reactjs.org/).** If you have never used React before, that's fine -- it's quite easy to learn. Before continuing with this tutorial, complete the [Intro To React tutorial](https://reactjs.org/tutorial/tutorial.html).

Although Empirica's backend was build using the [Meteor](https://www.meteor.com/) framework, you will only need to use pure JavaScript to develop the backend of your experiment. This will become clearer later on in the tutorial.

The design philosophy of Empirica is to handle for you all the boring logistics and allowing you to get straight to what really interests you, whatever that may be. So it was built with the experiment developer in mind. Your time should not be spent in implementing reinventing the wheel every time you try to experiment with your ideas.


All the code for the project that you will build during the tutorial can be found [here]. If you have questions, comments, or suggestions, please add a Github issue to that repo.

## Quick Start 

First of all, You will need Meteor, for which you can find installation instruction [here](https://meteor.com/install).

Then, you will need to clone Empirica's default app that comes bundled when you clone or fork the repository. From the terminal:
```
git clone https://github.com/empiricaly/empirica.git
```
Then `cd empirica` and run `meteor npm install` to update local npm dependencies. Now you can start the
local webserver by running `meteor`. Then open a browser and navigate to http://localhost:3000/ to verify that all is working properly. You should see the following:

![screenshot](/img/noExperiments.png)

[ ![screenshot][ts-img] ]

[ts-img]: /img/noExperiments.png


