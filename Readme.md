Introduction
For this project, you will work with the Reacher environment.

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.


Solving the Environment
Note that your project submission need only solve one of the two versions of the environment.

Option 1: Solve the First Version
The task is episodic, and in order to solve the environment, your agent must get an average score of +30 over 100 consecutive episodes.

Option 2: Solve the Second Version
The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically,

After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
This yields an average score for each episode (where the average is over all 20 agents).
The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30.

I used second version, and now, it is working successfully!!

# DRL - DDPG - Reacher Continuous Control
Udacity Deep Reinforcement Learning Nanodegree Program - Reacher Continuous Control


### Observations:
- To run the project just execute the <b>main.py</b> file.
- There is also an .ipynb file for jupyter notebook execution.
- If you are not using a windows environment, you will need to download the corresponding <b>"Reacher"</b> version for you OS system. Mail me if you need more details about the environment <b>.exe</b> file.
- The <b>checkpoint.pth</b> has the expected average score already hit.


### Requeriments:
- tensorflow: 1.7.1
- Pillow: 4.2.1
- matplotlib
- numpy: 1.11.0
- pytest: 3.2.2
- docopt
- pyyaml
- protobuf: 3.5.2
- grpcio: 1.11.0
- torch: 0.4.1
- pandas
- scipy
- ipykernel
- jupyter: 5.6.0

### The hyperparameters:
- The file with the hyperparameters configuration is the <b>main.py</b>. 
- If you want you can change the model configuration to into the <b>model.py</b> file.
- The actual configuration of the hyperparameters is: 
  - Learning Rate: 1e-4 (in both DNN)
  - Batch Size: 128
  - Replay Buffer: 1e5
  - Gamma: 0.99
  - Tau: 1e-3
  - Ornstein-Uhlenbeck noise parameters (0.15 theta and 0.2 sigma.)

- For the neural models:    
  - Actor  
  
    - Hidden: (input, 1024) - ReLU
    - Hidden: (1024, 512)   - ReLU
    - Hidden: (512, 256)    - ReLU
    - Hidden: (256, 128)    - ReLU
    - Output: (128, 1)      - TanH

  - Critic
 
    - Hidden: (input, 1024)                - ReLU
    - Hidden: (1024 + action_size , 512)   - ReLU
    - Hidden: (512, 256)                   - ReLU
    - Hidden: (256, 128)                   - ReLU
    - Output: (128, 4)                     - linear
    
