# dqn_cartpole
Toyproject from Reinforcement Learning class

# Introduction
To get basic understanding of Reinforcement Learning and its usage in Deep Neural
Network, DQN can be one of the entry level implementations needed. OpenAI gym provides
various models and environments where the simulation can be done and viewed. Cartpole is an
environment where the agent has to keep a pole, that is attached by an un-actuated joint to a
cart, from falling over. The goal is to use this environment to implement DQN and see how the
agent learns by observing the simulation.
# Environment (Cartpole-v1)
Cartpole-v1 provides an environment where a pole is attached by an un-actuated joint
to a cart which moves along a frictionless track. The pendulum starts upright and the goal is to
apply force of +1 or -1 to the cart to prevent it from falling over. A reward of +1 is given for
every timestep that the pole remains upright. The episode ends when the pole is more than 15
degrees from vertical or the cart moves more than 2.4 units from the center.
# Model (Deep Q-Network)
Deep Q-Network approximate state-action value Q through Deep Learning. However,
there exist challenges when applying Reinforcement Learning in Deep Learning. One is that
Deep Learning learns with labeled data while Reinforcement Learning learns with rewards that
comes after certain amount of time which makes it harder for model to learn. Also, Deep
learning assumes data to be independent while Reinforcement Learning has states that have
correlation to each other, violating the assumption of Deep Learning.
Due to the challenges like above, DQN suggests a method called Experience Replay
where the model learns from a data set of Current State, Action, Reward and Next State during
every time-step. By randomly selecting from the data set, it not only reduces the correlation
problem but also re-use the data. The Experience-Replay Buffer carries certain amount of
samples and when the buffer is full, it replaces some of the data with new samples.
# Conclusion
With simple network trained with 10000 episodes, Cartpole learned to keep the
pendulum upright for 7seconds. The result is rather unsatisfying and I think this is due to a
noise that comes from overestimation of action-value due to max operator in a process of
approximation. This can be seen in the score that fluctuates a lot in the training. To summarize,
DQN does seem to train okay in Deep Learning setting but needs more of error reducing
technique for better performance.
