# Turlesim Catch Them All

This is the last exercise propoused on the course "ROS2 for begginers" of Edouard Renard on the Udemy platform.
The goal to this exercise is to put in practise the knowlledge gained in the course lessons by creating a simoulation on the turtlesim. That simulation consists of spawning turtles randomly around the map and making the master turtle go to their position and catch them.

### The goal

Altough that was the main goal of the exercise, mine was a bit further away.
My main goal was to abstract ROS2 funcionalites lectured in the course (clients, services, publishers, subscribers and timmers) to classes I could use a in maore simpler, intuitive and safer way. While doing all the dirty work automatically behind the scenes.
Those abstractions can be found on the utilities folder configured as libraries to be used around the project.

I also focused on the architecture and project design. Was able to use the CMakelists in a much simpler and clean way. So I dont need to have huge blocks of repeated code. This organiztion and management is more flexible and can even be used with CMake based IDE's such as clion.

### The project

This project consists of two main nodes:

- TurtleControllerNode - This node controlls  the master turtle and is formed of three main pieces:
    
  - CatchTurtleClient - Sends the request to remove the spawned turtles from the map  as soon as the master tuertle reaches their positions, and it's located on the TurtleInteractions module.
      
  - TurtleInteractions - Manages all the interactions and comunications that TurtleController needs to have (client, publishers and subscribers).
      
  - TurtleMoveCenter - Manages all the movement and coordinats related tasks such as calculating distances, the next move and the closest target.

- TurtleSpawnerNode - This node manages the spawned turtles and consists of two clients and a service:

  - TurtleSpawnClient - Sends a request to turtlesim to spawn a turtle on the required coordinates.

  - KillClient - Sends a request to turtlesim to kill (remove) catched turtles.
 
  - CatchTurtleService - Recieves the CatchTurtleClient request and activates the KillClient
