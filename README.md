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

## frozenlake.py - contains the FrozenLakeEnv class
## Dynamic_Programming.ipynb - the mini project notebook where you will write all of your implementations (this is the only file that you will modify!)
## check_test.py - contains unit tests that you will use to verify that your implementations are correct
## plot_utils.py - contains a plotting function for visualizing state-value functions


Note that it is broken into parts, which are designed to be completed at different parts of the lesson. For instance, you will complete Parts 0 and 1 in the concept titled Mini Project: DP (Parts 0 and 1). Then, you should wait to complete Part 2 until you reach the Mini Project: DP (Part 2) c

To peruse the other files, you need only click on "jupyter" in the top left corner to return to the Notebook dashboard.
