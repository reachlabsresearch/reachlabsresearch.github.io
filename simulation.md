---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Learning to Simulate Reality
description: Page description

# Author box
author:
    title: About Author
    title_url: '#'
    external_url: true
    description: Author description
    hello: test

# Micro navigation
micro_nav: true

# Page navigation
page_nav:

    next:
        content: Next page
        url: '../datafarm/index.html'
---


## Introduction

The recent successes of Deep Learning have been fuelled by massive amounts of data. Waymo’s vehicles record 5000 miles per day, OpenAI Five played Dota 2 for cumulative centuries before reaching world-class, and AlphaZero played 40 million games of Go before being able to beat the world's best players.

Despite this, real-world robotics research has been limited to comparatively small datasets.

The first challenge is to build up a farm of robots that can collect more data than ever before. Commercial robotic arms cost about $30K each, so we will have to figure out a way to lower the cost of dextrous robots by 100X.

## Subgoals

1. [Design robot structure and electronics.](#subgoal1) (DONE 18-9-2018)
2. [Source all parts.](#subgoal2) (DONE 19-9-2018)
3. Build first prototype robot.
4. Write control software.
5. Build basic middleware library for control and viewing.
6. Teleoperate well enough to stack lego blocks.
7. Build five robots.
8. Write distributed control library.
9. Build initial datafarm of 15 robots. (0/15)
10. Get training with a toy test task.


## 1. Design robot structure and electronics.
{: #subgoal1 }
We need a robot with mm repeatability, zero backlash, a 1kg payload, force sensing/control, and a workspace of about half a meter cubed (with minimal kinematic dead zones). The entire robot (including camera and electronics) should cost less than 300 USD and be trivial to assemble and modify.

The only robotic architecture that can satisfy these constraints is a [cable robot](). A cable robot is essentially a hollow box containing a floating end-effector which is held in place by cables from the corners. By changing the length of each cable and measuring their tensions you can control the position and force of the end-effector.

The reason that people don't typically use cable robots is that they're very hard to get working. Every cable has to be perfectly taut at all times, and the structure typically has to be built to extremely high accuracy. There are only a handful in existance, and none have left the lab. Making these is hard, but if you can figure out a smart way to autocalibrate on-the-fly with a closed feedback loop, then you would have a highly accurate and incredibly cheap robot.

There aren't any cable robot designs already online so we'll have to make our own.

Here's the first design:
