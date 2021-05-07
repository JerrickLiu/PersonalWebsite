---
layout: post
title: 'My love (and maybe hate?) relationship with MineRL. '
published: true
---

When I heard the idea that I could teach an A.I. agent to play Minecraft, I was immediately swooned by it. They showed me the reinforcement learning library [MineRL](https://minerl.io/docs/index.html) which has a dataset of over **60 million frames** of recorded human player data. Now that's a dataset. It's also 60 GB mind you. The purpose of the MineRL is for research yes, but also for a [competition](https://minerl.io/competition/) where users can upload their code to a platform called Alcrowd and once uploaded, the servers train agents using their code and evaluate the reward, with the highest reward winning. I'm not at the point with my code where I can be competitive, but it sounds super sweet and I one day want to participate in it. As I'm writing this right now, the 2020 competition just started and ronund 1 has 76 days left. 

Check it out on their [website](https://www.aicrowd.com/challenges/neurips-2020-minerl-competition)

MineRL labs was created at Carnegie Mellon University, one of the leading schools in A.I. research. Anywho, that isn't what the main point of this blog post is. The main point is talking about my experience with MineRL. So MineRL uses dictionary action and observation spaces. What are action and observation spaces? MineRL is base of the environment structure of [OpenAI Gym](https://gym.openai.com). 

Gym is very useful in the sense that it provides environments or skeletons of environments (which you can modify to fit your needs like in MineRL) and all you need is your RL algorithm. Actions and observations are very important concepts in the world of RL. Actions are easy enough: It's the action that the agent takes in the environment. The observation is what the environment returns to the agent along with the reward after each action. For example, in MineRL, the observation is a RBG pixel. In Gym, they're grouped into action and observation spaces: the **structure** of the possible actions and observations in the environment. So back to what I was saying, MineRL contains dictionary observation and action spaces containting keys which correspond to what actions the agent can take. 

Here's an example of an obervation and action space for the MineRLTreechop-v0 environment, where the goal was to obtain 64 logs of wood from cutting down trees. 

```python

Dict({
    "pov": "Box(low=0, high=255, shape=(64, 64, 3))"
})

Dict({
    "attack": "Discrete(2)",
    "back": "Discrete(2)",
    "camera": "Box(low=-180.0, high=180.0, shape=(2,))",
    "forward": "Discrete(2)",
    "jump": "Discrete(2)",
    "left": "Discrete(2)",
    "right": "Discrete(2)",
    "sneak": "Discrete(2)",
    "sprint": "Discrete(2)"
})
```

In python dictionaries, there are key-value pairs. The keys in the dictionary represents the actions themselves: attack, back etc. The value of each key represents the action space of that action. It's nested. The action space (remember, the structure) for the entire environment is a dictionary. Each key represents an action, and the value for each key is another action space. Moving forward, what does discrete and box mean? Well, those are other types of action spaces just like the dictionary type. Think of discrete as binary. 1 means the action is activated, 0 means its not. Which makes sense. For example, if the action chosen is attack, our RL agent eventually learns that when its near a tree or near a zombie, we should choose "1", or to actually attack. Box on the other hand represtents a range of possible values. In this case, the camera action (the agent moving the camera around) is a box action space with low of -180 and high of 180 and can go anywhere bwetween the two to move around the camera. 

Sounds simple enough right? Well, yeah, but a big problem that I ran into early on was that the [repo of algorithms](https://github.com/hill-a/stable-baselines) that I used doesn't support dictionary spaces. So from the beginning, there was a lot of technical problems to overcome, mainly, how to do we convert the dictionary space to a box or discrete space? The answer?

> Wrappers

Wrappers play a huge part in designing your own environments to be able to implement RL algorithms on them. Wrappers will allow us to add functionality to environments, such as modifying observations and rewards to be fed to our agent. It's common in reinforcement learning to preprocess observations in order to make them more easy to learn from. A common example is when using image-based inputs, to ensure that all values are between 0 and 1 rather than between 0 and 255 as is more common with RGB images. Wrapping the observation space was easy enough - we just needed the "pov" key from the dictionary. 

```python
env = gym.make("MineRLTreechop-v0")
observation_space = env.observation_space.spaces['pov']
```

A very short snippet of code that shows how the observation "dict" space is modified to return the value of the key of "pov" which is the box space of the agent's POV. The action space was slightly more challenging, but the concept was the space. We wanted to obtain the values of each of the keys inside the dictionary observation space. The concept of the dictionary observation space is effective, nice, and personally for this Minecraft environment easier to work with and undertand if you're not using some baseline algorithm. However, that does require you to modify RL algorithms but I'm not at that level yet. Instead we chose to wrap it.

## Good, now the observation and action space is compatible with our baselines algorithms. Let's start training! All is well! Right?

Well, I wish it was as easy as that, but because Minecraft is so incredibly complex, it would take forever for the RL agent to learn something useful, if anything at all. If only we could speed it up?

> Queue imitation learning

Read future posts to find out more on my progress! 

