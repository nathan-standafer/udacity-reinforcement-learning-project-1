#  Navigation project submission for Udacity Deep Reinforcement Learning Nanodegree

A Deep DQN implementation to navigate the Unity Banana Collector environment provided by Udacity.

### The Environment
The project environment is visualized as a 3D space where bananas must be collected by moving over them.  Yellow bananas receive a reward of 1, while brown bananas have a reward of -1.  The state space consists of 37 continuous values representing the location of the bananas relative to the actor.  Possible actions are forward, left, right, and backwards.  The environment is considered solved when a total reward of 13 is achieved over 300 steps.

The environment can be setup by following the instructions [here](https://github.com/udacity/deep-reinforcement-learning/tree/master/p1_navigation#getting-started)

### The Approach Used
This implmentation utilizes a Reinforcement Learning Double DQN strategy.  The notebook describes the networks used and how they are trained.  The model is relatively simple, with three layers:  input, hidden, and output.  ReLU activation functions are applied to the input and hidden layers.  The output of the model estimates a discounted future reward for each possible action.

The main hyperparameters used are as follows:
 - gamma:  0.99
 - TAU (target model update factor): .005
 - eposilon: Starting at 0.9 and decaying 0.05  Note, the code in the notebook mignt not represent these numbers as I had to run the trainng loop multiple times to allow the score to be maximized.
  - learning rate:  an Adam optimizer with a learnign rate of .0004
  - batch size:  64
  - epochs: 800 epochs with 10 games played for each epoch.  4 training batches were performed after each game played.  
  
### Possible improvements
My initial approach utilized only a DQN, not a Double DQN.  With a DQN, I was not able to reach the desired score.  The agent was much more effective after applying the Double DQN strategy.  I would have never thought of something like the Double DQN myself, which shows the value of taking courses and reading papers on how to implement such strategies.

Other possible apporaches are prioritized experince replay and a utilizing dualing networks.  Prioritized experince replay would replace the random selection of steps from the replay memory with an algorithim that prioritizes the replay steps that had the greatest error.  Dualing DQN networks break the netork into two outputs: one to estimate the value of the state and one to define the advangate of the actions

### Results
All code is in the TrainBananaBrain notebook.  I tried to keep the code as short and simple as possible with comments to focus on my implemenation of the Double DQN.

This implementation achieves a score of over 14 in about 2400 playthoughs.

As seen in the chart below, the agent reached its peak at about epoch 600.  This is probably because the agent starteed to reach the maximum score possible after the environment's 300 step limit.


![training](https://github.com/nathan-standafer/udacity-reinforcement-learning-project-1/raw/master/score%20vs.%20epoch.png)
