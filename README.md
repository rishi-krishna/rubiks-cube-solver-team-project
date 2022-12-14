# Feature-Based Reinforcement Learning: Solving the Rubik's Cube

*"A generally intelligent agent must be capable of learning to solve issues in complex domains with little assistance from humans."*
This project is an attempt to represent and solve the 3X3 Basic Rubik's cube

To solve the problem of a Rubik's cube, we implemented feature-based Q-Learning, a powerful reinforcement learning technique, as well as the utilization of a pattern database, to quantify the quality of near-finished cubes
Q learning is a model-free reinforcement algorithm where the goal of the agent is to determine the optimal policy, or plan, to take them from the starting state to the goal state. The ‘q’ in q-learning stands for quality. Quality in this case represents how useful a given action is in gaining some future reward.
When q-learning is performed we create what’s called a q-table or matrix that follows the shape of [state, action] and we initialize our values to zero. We then update and store our q-values after an episode. This q-table becomes a reference table for our agent to select the best action based on the q-value.

This project assumes that a Rubik's cube can only execute 180 degree side turns, which greatly reduces the branching factor* of the cube's state space tree

This project also attempts to reach a solution for a solved cube which has had "n random moves executed on it", this value n
currently can be up to 5 to find a goal state for each execution, or in the range of 6-10 to be somewhat successful

> "puzzle.py" includes the state representation of a Rubik's Cube, "State()", as well as a few auxillary functions
that are used elsewhere in the application

> "tests.py" and "others.py" includes a variety of test cases that can be executed to confirm the valid implementation of the cube's state represention

> "Agent.py" includes the implementation of a reinforcement learning agent, which executes iterations of Q-Learning, and additionally uses a pattern database, to build up a Q-Table, which is used to eventually try to solve the given random Rubik's cube

### Using this project

clone the repository and verify you have python3 installed 

`>>> python Agent.py (will run Q-Learning on a n=5 scrambled cube, and attempt to solve it) `

to change the number of moves to apply to the initial cube, change **n=5** to any value on the line 23 in Agent.py

`>>> self.start_state = cube if cube is not None else n_move_state(n=5) `

References:

Solving the Rubik's Cube without Human Knowledge: https://arxiv.org/pdf/1805.07470.pdf

Reinforcement Learning to solve Rubik’s cube: https://medium.com/datadriveninvestor/reinforcement-learning-to-solve-rubiks-cube-and-other-complex-problems-106424cf26ff

## Created by: Rishi Krishna Thodupunuri, Naga Pradeep Motupalli, Susmitha Pathi 

