# OpenAI-Gym-FrozenLakeEnv
OpenAI Gym: FrozenLakeEnv
In this lesson, you will write your own Python implementations of all of the algorithms that we discuss. While your algorithms will be designed to work with any OpenAI Gym environment, you will test your code with the FrozenLake environment.


Source: http://eskipaper.com/images/frozen-lake-6.jpg

In the FrozenLake environment, the agent navigates a 4x4 gridworld. You can read more about the environment in its corresponding GitHub file, by reading the commented block in the FrozenLakeEnv class. For clarity, we have also pasted the description of the environment below:

    """
    Winter is here. You and your friends were tossing around a frisbee at the park
    when you made a wild throw that left the frisbee out in the middle of the lake.
    The water is mostly frozen, but there are a few holes where the ice has melted.
    If you step into one of those holes, you'll fall into the freezing water.
    At this time, there's an international frisbee shortage, so it's absolutely imperative that
    you navigate across the lake and retrieve the disc.
    However, the ice is slippery, so you won't always move in the direction you intend.
    The surface is described using a grid like the following
        SFFF
        FHFH
        FFFH
        HFFG
    S : starting point, safe
    F : frozen surface, safe
    H : hole, fall to your doom
    G : goal, where the frisbee is located
    The episode ends when you reach the goal or fall in a hole.
    You receive a reward of 1 if you reach the goal, and zero otherwise.

    """"
The Dynamic Programming Setting
Environments in OpenAI Gym are designed with the reinforcement learning setting in mind. For this reason, OpenAI Gym does not allow easy access to the underlying one-step dynamics of the Markov decision process (MDP).

Towards using the FrozenLake environment for the dynamic programming setting, we had to first download the file containing the FrozenLakeEnv class. Then, we added a single line of code to share the one-step dynamics of the MDP with the agent.


    """"
    # obtain one-step dynamics for dynamic programming setting
    self.P = P
    """
The new FrozenLakeEnv class was then saved in a Python file frozenlake.py, which we will use (instead of the original OpenAI Gym file) to create an instance of the environment.





# Your Workspace
You will write all of your implementations within the classroom, using an interface identical to the one shown below. Your Workspace contains four files:

### frozenlake.py - contains the FrozenLakeEnv class
### Dynamic_Programming.ipynb - the mini project notebook where you will write all of your implementations (this is the only file that you will modify!)
### check_test.py - contains unit tests that you will use to verify that your implementations are correct
### plot_utils.py - contains a plotting function for visualizing state-value functions






## Overview

### Details
* Name: FrozenLake-v0  
* Category: Classic Control
* [Leaderboard Page](https://github.com/openai/gym/wiki/Leaderboard#FrozenLake-v0)
* Old links:
  * [Environment Page](https://gym.openai.com/envs/FrozenLake-v0)  
  * [Algorithms Page](https://gym.openai.com/algorithms?groups=classic_control)

### Description
The goal of this game is to go from the starting state (S) to the goal state (G) by walking only on frozen tiles (F) and avoid holes (H). However, the ice is slippery, so you won't always move in the direction you intend (stochastic environment)

### Source
Came from this Colab and blog
[Blog](https://colab.research.google.com/drive/1oqon14Iq8jzx6PhMJvja-mktFTru5GPl#scrollTo=5aQKQMJTJBPH)


## Environment

### Observation
Type: Discrete (16)

Num | Observation (State)
---|---
0 - 15 | For 4x4 square, counting each position from left to right, top to bottom

### Actions
Type: Discrete(4)

Num | Action
--- | ---
0 | Move Left
1 | Move Down
2 | Move Right
3 | Move Up

### Reward
Reward is 0 for every step taken, 0 for falling in the hole, 1 for reaching the final goal

### Starting State
Starting state is at the top left corner

### Episode Termination
1. Reaching the goal or fall into one of the holes
2. The environment also returns `done` if it has stepped 100 times.

### Solved Requirements
Reaching the goal without falling into hole over 100 consecutive trials.
