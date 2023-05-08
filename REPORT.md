Learning Algorithm.
    Used DDPG which is deep deterministric policy gradient. This algorithm combine policy based method and value based method, especially policy gradient(actor) and deep q-learning algorithm(critic). The neural network is improved its learning process with using target network for each actor and critic and this helps to prevent overlearning or polarized learning. Moreover, the replay buffer also helps to learn in reliable learning process. 
    
Hyperparameters
    replay buffer size: 1e6
    max timesteps: 3000 (all episodes get shutdown after 3000 timesteps)
    minibatch size: 256
    discount factor: 0.99
    tau (soft update for target networks factor): 1e-3
    learning rate: 1e-4 (actor) and 1e-3 (critic)
    update interval (how often to learn): 2
    beta start (factor for the noise added to the actions selected by the actor): 0.1
    beta decay factor: 0.995
    min beta: 0.01
    
The actor model is a simple feedforward network:

    Batch normalization
    Input layer: 33 (input) neurons (the state size)
    1st hidden layer: 128 neurons (relu)
    2nd hidden layer: 128 neurons (relu)
    output layer: 4 neurons (1 for each action) (tanh)
    The critic model:

    Batch normalization
    Input layer: 33 (input) neurons (the state size)
    1st hidden layer: 132 neurons (action with action_size 4 added) (relu)
    2nd hidden layer: 128 neurons (relu)
    output layer: 1 neuron
    
Result
    ![result](result_graph.jpg)
    
Future improvements
    In my opinion, in critic term, the double q learning can improve the action choose. And the actor term, the procimal policy optimization can help to improve the simulation. Because the learning seems to become unstable when the update rate is fast. But each episode is pretty long to gether enough trial data, these learning improvement can prevent unstable score.
