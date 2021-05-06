---
layout: post
title: Reinforcement learning is tough.
published: true
---
### Speaking from a recent graduate of high school

So I just graduated high school without ever taking a computer science or coding class. It was mainly through my own learning and exploration did I start to get into this field. And trust me, I love it. Reinforcement learning, at least my limited understanding of it right now, involves training a model or an agent to make decisions in an environement, both short-term and long-term, that maximizes the cumulutivate reward in said environment. 
#### Minecraft
This year, for example, I'm working with Minecraft agents. The agent is the A.I. playing Minecraft, and the environment is the world the A.I. spawns in. Depending on what you make the goal for the agent to be, the goal is to train the agent to take steps to reach that goal. How does the agent learn? That's where reward comes in. Every action the agent takes, ex. chop a wood block, break a dirt block, build a crafting table, the environment returns a reward and by using various reinforcement learning algorithms, we're able to maximize that reward. But coming straight out of high school without even taking advanced math courses such as Calculus 3 or linear algebra, it's hard to understand these deep learning techniques. For example, I'm currently using a reinforcement learning algorithm called Proximal Policy Optimization, or PPO for short. 

Here's the general mathematical theory behind it

![an image alt text]({{site.baseurl}}/images/ppo.png)

Anyone who doesn't have a decent understanding of math won't be able to understand that. Luckily, our high school offers math up to Calculus 2 so I was able to understand it. And for those who want to get started in machine learning, you got to have a strong foundation in math. That was a key takeway right from the get go when I started all of this. 

#### PPO and OpenAI Spinning Up

From my limited understanding (notice how I keep saying limited? I just started all of this stuff recently BTW so I'm writing this blog to

1. really see if I can understand it. If I can write about it here explaining it, then I think 	I've made some progress learning. And
2. emphasize how you probably shouldn't rely on me for your reinforcement learning 				   tutorial. 
  
This is more so me explaining it to myself. Sort of. I do, however, recommend the [OpenAI Spinning Up tutorial](https://spinningup.openai.com/en/latest/user/introduction.html) which is absolutely fantastic for those wanting to get into reinforcement learning. It certainly has helped me a ton. (You're welcome OpenAI for plugging your course! I kid of course.) Anyway, back to PPO. PPO utilizes policy optimization. But what is a policy? Remember how we want to train the agent to take the action that maximizes reward? This is what the policy is. The policy returns the action that maximizes the reward. The policy we want an agent to learn basically becomes its brain. And in policy optimization types of RL algorithms like PPO, we directly optimize that policy to maximize reward for our goals. However, PPO is a bit different. In proximal policy optimization, at least the way I understand it, is instead of directly maximizing the policy function, we maximize a surrogate objective function, with this objective function giving a conservative estimate for how much the reward will change with each action. And I say conservative because PPO limits big changes to your policy function which could potentially be disastrous in your training. That's the gist of it. It may not be explained well so I'm going to leave it to the actual people who come up with PPO. [Here's the link to their paper](https://arxiv.org/abs/1707.06347). Wow, that was a hefty second post! Not what I expected. If you read untill the end, you most likely are interested in my work or machine learning and if so great! Because I'd find all of this stuff quite dull and not understandable if I had no background in computer science. And if you're my reseach mentors reading this, did I make you proud?
