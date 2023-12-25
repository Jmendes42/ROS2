# Turlesim Catch Them All

This is the last exercise propoused on the course "ROS2 for begginers" of Edouard Renard on the Udemy platform.
The goal to this exercise is to put in practise the knowlledge gained in the course lessons by creating a simoulation on the turtlesim. That simulation consists of spawning turtles randomly around the map and making the master turtle go to their position and catch them.

### The goal

Altough that was the main goal of the exercise, mine was a bit further away.
My main goal was to abstract ROS2 funcionalites lectured in the course (clients, services, publishers, subscribers and timmers) to classes I could use a in maore simpler, intuitive and safer way. While doing all the dirty work automatically behind the scenes.
Those abstractions can be found on the utilities folder configured as libraries to be used around the project.

I also focused on the architecture and project design. Was able to use the CMakelists in a much simpler and clean way. So I dont need to have huge blocks of repeated code. This organiztion and management is more flexible and can even be used with CMake based IDE's such as clion.

