This documentation is being updated continually and is subject to change. If you see anything missing, use the Edit on GitHub button at the top right of every page to suggest improvements.


# Basic Tutorial: Guess the Correlation Game
[Empirica](https://empirica.ly/) is an open-source JavaScript framework for running multiplayer interactive experiments and games in the browser. This tutorial walks you through building a simple, but a fully functional experiment that demonstrates many of the core features of Empirica. 

This will guide you step by step, from installing and running a local instance to deploying and testing your first Empirica experiment in the real world. For this tutorial, we will build a multiplayer and interactive 'Guess the Correlation' game. This is similar to the experiment we used for our paper: [The Wisdom of the Network: How Adaptive Networks Promote Collective Intelligence][1]
 
 [1]: https://arxiv.org/abs/1805.04766

The intended audience for this tutorial is someone who:

1. **Is familiar with experiment design** and understanding what we mean by random assignment, treatments, independent variables.

2. **Knows the basics of the JavaScript and [React](https://reactjs.org/).** If you have never used React before, that's fine -- it's quite easy to learn. Before continuing with this tutorial, complete the [Intro To React tutorial](https://reactjs.org/tutorial/tutorial.html).

Although Empirica's backend was build using the [Meteor](https://www.meteor.com/) framework, you will only need to use pure JavaScript to develop the backend of your experiment. This will become clearer later on in the tutorial.

The design philosophy of Empirica is to handle for you all the tedious logistics and allowing you to get straight to what interests you, whatever that may be. So it was built with the experiment developer in mind. Your time should not be spent in implementing reinventing the wheel every time you try to experiment with your ideas.


All the code for the project that you will build during the tutorial can be found [here]. If you have questions, comments, or suggestions, please add a Github issue to that repo.

## Quick Start 

First of all, You will need Meteor, for which you can find installation instruction [here](https://meteor.com/install).

Then, you will need to clone Empirica's default app that comes bundled when you clone or fork the repository. From the terminal:
```
git clone https://github.com/empiricaly/empirica.git
```
Then `cd empirica` and run `meteor npm install` to update local npm dependencies. Now you can start the
local webserver by running `meteor`. Then open a browser and navigate to http://localhost:3000/ to verify that all is working properly. You should see the following:

![no-experiment-img][no-experiment-img]

[no-experiment-img]: ./img/noExperiments.png

The default path `/` is what will the experiment participant see. In this case, if a participant would try to join your experiment now, they will be shown a message indicating that there are no available experiments.

Let's change that. There is another path where the experiment designer can configure and monitor the experiment. Navigate to `http://localhost:3000/ admin`. You will be prompted to enter a username and password. The login credentials can be found in `/import/core/startup/server/bootstrap.js`.

We highly recommend that you change the username and password in the `bootstrap.js' file and then reset your app using `meteor reset' from the terminal (you have to do `meteor reset` when you are inside the `empirica/` directory). After you are logged in, you should see the following:

![adminUI][no-adminUI-img]

[no-adminUI-img]: ./img/adminUI.png


Now go to ***conditions*** from the navigation bar. A condition (also called a factor, a dimension, or an independent variable) is a variable that will be manipulated by the experimenter. Empirica requires having the number of players as a mandatory condition. This is how many people will belong to the same instance of the game. All other conditions are experiment specific. 

For now, let's try different values for the `playerCount`.  1 player (i.e., solo game) to a small group (3 players) to a larger group (12 players). We can add these values by clicking on the `+` next to the `playerCount` condition. 

![conditions][conditions-img]

[conditions-img]: ./img/conditions.png

