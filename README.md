#  Navigation project submission for Udacity Deep Reinforcement Learning Nanodegree

A Deep DQN implementation to navigate the Unity Banana Collector environment provided by Udacity.

This impelmentation utilizes a Double DQN stragety to achieve a score of over 14 in about 2400 playthoughs.

All code is in the TrainBananaBrain notebook.  I tried to keep the code as short and simple as possible with comments to focus on my implemenation of the Double DQN.

I ran the code within the privided Udacity training environment.  I had a hard time getting it to run on my PC.  Executing the first cell in the notebook sets up the necessary dependencies when ran on the Udacity environment.

As seen in the chart below, the agent reached its peak at about epoch 600.  This is probably because the agent starteed to reach the maximum score possible after the environment's 300 step limit.


![training](https://github.com/nathan-standafer/udacity-reinforcement-learning-project-1/raw/master/score%20vs.%20epoch.png)
