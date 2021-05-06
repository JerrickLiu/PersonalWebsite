---
layout: post
title: 'Dockerfiles, images, containers, and my experience with them'
published: true
---
## What the heck is Docker?

I had heard of the term "docker" said throughout my coding career, but never looked into it and had any relevant experience with it. Not until now. But before I explain what I did with Docker, let me explain what Docker is first. [Docker](https://www.docker.com/), in short, allows you to basically "package" your code into neat little things called "docker images and docker containers" where you can distribute your software to other machines and servers and run your code without having to install anything externally on said machines and servers. Pretty cool, right? From my experience with it and writing dockerfiles, which then are built into docker images, which when run creates a docker container for the code to run, it has become to be a very powerful tool. 

## Writing dockerfiles

So the first step when getting started with Docker is to install Docker. I'll leave it to [Docker's website](https://docs.docker.com/desktop/) for the installation tutorial. But once installed, you can start running your own dockerfiles! When I wrote my first dockerfile, it was very simple. It just printed "hello world!". 

```bash
FROM python:3.6

RUN echo hello world! 
```


And that was it. After building it using the ```docker build``` command to build the dockerfile into a docker image I wrote and then using ```docker run``` to run an instance of the docker image, it successfully outputs "hello world!". Pretty cool! 

Packaging your code, however, is a bit more difficult. First, your code has many installations. For example, my code to run MineRL needed many installations: Python, Java (to run Minecraft), stable-baselines (the repo of algorithms I'm using), and various other libraries. So I had to make sure to install these through terminal commands in the dockerfile. Writing a ```requirements.txt``` file for my code really helped optimize the dockerfile, as instead of writing ```pip install some-library``` I could just do ```pip install -r requirements.txt``` which installed all the necessary libraries for the script to run. I recommend writing a ```requirements.txt``` file for any project that requires a decent amount of external libraries to be installed. Alternatively, an ```environment.yml``` file can be created for Anaconda environmnets which is also very helpful. However, I didn't want to go through all the extra work of downloading Anaconda and creating an anaconda environment for the script to run so I stuck with the pip route. 

## Dockerfile written! Time to run Minecraft!

So after some work, I had my very own dockerfile written. Take a look at it!
```
FROM nvidia/cuda:10.2-base-ubuntu18.04


MAINTAINER Jerrick Liu

LABEL description="Running MineRL headless"

WORKDIR /current/project/path/

RUN apt-get update && apt-get install -y \
cmake \
openjdk-8-jdk \
openssh-server \
libxrender-dev \
libopenmpi-dev \
zlib1g-dev \
x11-xserver-utils \
xvfb \
build-essential python3.6 python3.6-dev python3-pip python3.6-venv


# update pip
RUN python3.6 -m pip install pip --upgrade && \
        python3.6 -m pip install wheel

RUN pip3 install stable-baselines[mpi]
RUN pip3 install --upgrade minerl --user

COPY current/project/path/ ./project
COPY requirements.txt .
RUN pip3 install -r requirements.txt


CMD xvfb-run python3 /path/to/script
```
If you don't understand docker syntax, it might be bit confusing. But in short, when buidling the dockerfile that I wrote, it first runs all the installations required to run the script. It downloads Java, Python etc. And finally it runs the script. But if you notice, I have in the label "Running MineRL headless" and "xvfb-run python3" instead of just python3 and the path to the script. Why? Well, in order for Minecraft to run, you need software to render the actual gameplay of it. And since I'm writing a dockerfile and running the dockerfile on remote servers that don't necessarily have displays to show Minecraft on, I had make it run in headless mode (without a head. That is to say without a physical display). In order to sovle the problem, I used [Xvfb](http://elementalselenium.com/tips/38-headless) which allowed me to run my script without a physical display. Very useful. And after that was working, I had created my very first custom dockerfile that actually ran some pretty complex code. Thank you to my mentors for showing me the wonderful tool of Docker and I'm definitely going to carry that skillset to any future work I do!
