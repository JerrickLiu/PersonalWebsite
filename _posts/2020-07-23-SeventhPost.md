---
layout: post
title: Imitation learning!
published: true
---

## This is the queue 

So in an [earlier post](2020-07-11-ThirdPost.md), I talked about my experiences training Minecraft agents to chop trees using PPO and wrapping action and observation spaces into Box and discrete spaces so they'd be compatible with the algorithm. I left a little cliff hanger at the end where I talked about if there was only a way to speed up training and now here we are! Talking about how we sped up training! 

## Imitation learning/Behavior cloning

Imitation learning is very intuitive. Basically an A.I. agent learns to do a task through watching a human do it. We humans do that all the time to! For example, I play golf quite frequently and I used to have a swing coach. How he taught me was basically showing me each movement he did in his swing and told me to replicate that. Easier said than done of course, but that was, at it's core, how I learned: by imitating by swing coach. By watching him swing the golf club and in many times in slow-mo, I began to learn all the movements he was making in order to make a pure swing. And that's how agents can learn to. By combining supervised learning with reinforcement learning, we can train agents much faster. In Minecraft and the MineRL library, the dataset contains more than **60 million frames** of human gameplay. By taking advantage of that massive dataset, we utilized behavior cloning algorithms to teach the agents to learn by watching those frames of human gameplay. And by doing that, reward increased dramatically. Beforehand, it would take hours and hours for the agent to learn anything useful and by using behavior cloning, the agent started to learn to hit trees in only an hour! Very cool. 
