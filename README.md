# Deep Reinforcement Learning survey
This paper list is a bit different from others. I'll put some opinion and summary on it. However, to understand the whole paper, you still have to read it by yourself!   
Surely, any pull request or discussion are welcomed!

## Outline
- [Papers](https://github.com/andrewliao11/Deep-Reinforcement-Learning-Survey#papers)
- [Open Source](https://github.com/andrewliao11/Deep-Reinforcement-Learning-Survey#open-source)
- [Courses](https://github.com/andrewliao11/Deep-Reinforcement-Learning-Survey#course)
  - Python users
  - Lua users
- [Textbook](https://github.com/andrewliao11/Deep-Reinforcement-Learning-Survey#textbook)
- [Misc](https://github.com/andrewliao11/Deep-Reinforcement-Learning-Survey#misc)

## Papers
  - ***Deep Reinforcement Learning with Double Q-learning*** [[AAAI 2016]](http://arxiv.org/abs/1509.06461)
      - Hado van Hasselt, Arthur Guez, David Silver 
      - Deal with overestimation of Q-values
      - Separate action-select-Q and predict-Q 
  - ***Playing Atari with Deep Reinforcement Learning*** [[NIPS 2013 Deep Learning Workshop]](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)
      - Volodymyr Mnih, Koray Kavukcuoglu, David Silver, Alex Graves Ioannis Antonoglou, Daan Wierstra  
  - ***Human-level control through deep reinforcement learning***, [[Nature 2015]](http://home.uchicago.edu/~arij/journalclub/papers/2015_Mnih_et_al.pdf)
      - Most optimization algorithms assume that the samples are independently and identically distributed, while for reinforcement learning, the data is a sequence of action, which breaks the assumption.
      - Experience replay
      - Iterative update Q-value
      - [Source code [Torch]](https://sites.google.com/a/deepmind.com/dqn)
  - ***Asynchronous Methods for Deep Reinforcement Learning*** [[ICML 2016]](https://arxiv.org/abs/1602.01783)
      - Volodymyr Mnih, Adrià Puigdomènech Badia, Mehdi Mirza, Alex Graves, Timothy P. Lillicrap, Tim Harley, David Silver, Koray Kavukcuoglu 
      - Implementation from others:  [async-rl](https://github.com/muupan/async-rl)
      - [Asynchronous SGD](https://cxwangyi.wordpress.com/2013/04/09/why-asynchronous-sgd-works-better-than-its-synchronous-counterpart/)
      - [Tuning Deep Learning Episode 1: DeepMind's A3C in Torch](http://www.allinea.com/blog/201607/tuning-deep-learning-episode-1-deepminds-a3c-torch)
  - ***Learning Hand-Eye Coordination for Robotic Grasping with Deep Learning and Large-Scale Data Collection*** [[arXiv 2016]](http://arxiv.org/abs/1603.02199)
      - Sergey Levine, Peter Pastor, Alex Krizhevsky, Deirdre Quillen
      - [Deep Learning for Robots: Learning from Large-Scale Interaction](https://research.googleblog.com/2016/03/deep-learning-for-robots-learning-from.html)
  - ***Active Object Localization with Deep Reinforcement Learning*** [[ICCV 2015]](http://arxiv.org/abs/1511.06015)
      - Juan C. Caicedo, Svetlana Lazebnik
      - Agent learns to deform a bounding box using simple transformation action   
  - ***Dueling Network Architectures for Deep Reinforcement Learning*** [[ICML 2016]](http://arxiv.org/abs/1511.06581)
      - Ziyu Wang, Tom Schaul, Matteo Hessel, Hado van Hasselt, Marc Lanctot, Nando de Freitas   
      - Two stream network(state-value and advantage funvtion)
      - Focusing on innovating a neural network architecture that is better suited for model-free RL
      - Torch blog - [Dueling Deep Q-Networks](http://torch.ch/blog/2016/04/30/dueling_dqn.html)   
  - ***Memory-based control with recurrent neural networks*** [[NIPS 2015 Deep Reinforcement Learning Workshop]](http://arxiv.org/abs/1512.04455)
      - Nicolas Heess, Jonathan J Hunt, Timothy P Lillicrap, David Silver
      - Solve partially-observed problem  
  - ***Control of Memory, Active Perception, and Action in Minecraft*** [[arXiv 2016]](https://arxiv.org/abs/1605.09128)
      - Junhyuk Oh, Valliappa Chockalingam, Satinder Singh, Honglak Lee
      - Solving problem concerning to partial observability
      - Propose mincraft task
      - Memory Q-Network (MQN), Recurrent Memory Q-Network (RMQN), and Feedback Recurrent Memory Q-Network (FRMQN)
  - ***Continuous Control With Deep Reinforcement Learning*** [[ICLR 2016]](http://arxiv.org/abs/1509.02971)
      - Timothy P. Lillicrap, Jonathan J. Hunt, Alexander Pritzel, Nicolas Heess, Tom Erez, Yuval Tassa, David Silver, Daan Wierstra
      - Solves the continuous control task, and avoids the curse of **dimension**
      - **Deep** version of DPG(deterministic policy gradient)
      - When going deep, some issues will happens. It's unstable to use the non-linear function to approxiamate 
      - The different components of the observation may have different physical units and the ranges may vary across environments. => solve by batch normalization
      - For exploration, adding the noise to the actor policy: µ0(st) = µ(st|θt µ) + N
  - ***Deterministic Policy Gradient Algorithms*** [[ICML 2014]](http://jmlr.org/proceedings/papers/v32/silver14.pdf)
      - D. Silver, G. Lever, N. Heess, T. Degris, D. Wierstra, M. Riedmiller
      - **Highly recommended for learning policy network, and actor-critic algorithms**
      - In continuous action spaces, greedy policy improvement becomes problematic, requiring a global maximisation at every step. Instead, a simple and computationally attractive alternative is to move the policy in the direction of the gradient of Q, rather than globally maximising Q

## Open Source
### Python users[Tensorflow, Theano]
  - [OpenAI gym](https://gym.openai.com/)
    - RL **benchmarking** toolkit
    - Provide environment and evaluation metrics
  - [Keras](https://github.com/matthiasplappert/keras-rl)
    - Fully compatible with OpenAI
    - Some algorithms have been implement(e.g DQN, DDQN, DDPG, CDQN)
  - [TensorLayer](https://github.com/zsdonghao/tensorlayer)
    - Built on the top of Google TensorFlow
  - [rllab](https://github.com/rllab/rllab)
    - Fully compatible with OpenAI 
    - Continuous control tasks 
    - Nice to implement new algorothms
    - [Benchmarking Deep Reinforcement Learning for Continuous Control](https://arxiv.org/abs/1604.06778)
  - [KEras](https://github.com/osh/kerlym)
    - Built on keras
    - Fully compatible with OpenAI
    - Host a handful of agent of reinforcement learning agents
    - [Deep Reinforcement Learning Radio Control and Signal Detection with KeRLym, a Gym RL Agent](http://arxiv.org/abs/1605.09221)
  - [Deep Reinforcement Learning in TensorFlow](https://github.com/carpedm20/deep-rl-tensorflow)
    - Implemented by @carpedm20
    - Having some basic reinforcement algorothms

### Lua users[Torch]
  - [rltorch](https://github.com/ludc/rltorch), basic reinforcement learning package
  - [awesome-torch for reinforcement learning](https://github.com/carpedm20/awesome-torch#reinforcement-learning)
    - List of open sources for rerinforcement learning 

## Course
  - [CS 294: Deep Reinforcement Learning](http://rll.berkeley.edu/deeprlcourse/#related-materials)
      - Instructors: John Schulman, Pieter Abbeel
  - [UC Berkeley CS188 Intro to AI](http://ai.berkeley.edu/home.html)
      - [2013 Spring video](https://www.youtube.com/user/CS188Spring2013) on youtube   
  - [Advanced Topics: RL](http://www0.cs.ucl.ac.uk/staff/d.silver/web/Teaching.html)
      - Instructors: David Silver
  - [Deep learning videoes at Oxford 2015](https://www.youtube.com/playlist?list=PLE6Wd9FR--EfW8dtjAuPoTuPcqmOV53Fu)
      - Instructors: Nando de Freitas
      - lecture 15, 16 are strongly related to reinforcement learning
  
## Textbook
  - [Foundations_of_Machine_Learning](http://www.cs.nyu.edu/~mohri/mlbook/)
      - chapter 14: Reinforcement learning  
   
  
## Misc
  - [A collection of Deep Learning resources](http://www.jeremydjacksonphd.com/category/deep-learning/)
  - [Deep Reinforcement Learning: Pong from Pixels](http://karpathy.github.io/2016/05/31/rl/), from Andrej Karpathy' blog
      - policy gradient (very clear!)
  - [Guest Post (Part I): Demystifying Deep Reinforcement Learning](https://www.nervanasys.com/demystifying-deep-reinforcement-learning/)
  - [Reinforcement Learning and Control](http://cs229.stanford.edu/notes/cs229-notes12.pdf), lecture from Andrew Ng
      - basic reinforcement learning 
      - continuous state MDPs
  - [DEEP REINFORCEMENT LEARNING](https://deepmind.com/blog), from David Silver, Google DeepMind
      - briefly discuss some work done by deepmind
  - [What are the benefits of actor/critic framework in reinforcement learning?](https://www.quora.com/What-are-the-benefits-of-actor-critic-framework-in-reinforcement-learning)
      - Clearly expain the advantages of actor/critic 


