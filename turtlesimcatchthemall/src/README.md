# Turtlesim Catch Them All

This project represents the culmination of the "ROS2 for Beginners" course led by Edouard Renard on the Udemy platform. It aims to practically apply the knowledge acquired throughout the course by creating a simulation within the turtlesim environment. The simulation involves spawning turtles randomly across the map and orchestrating the movement of a master turtle to capture them.

## Objective

While the primary exercise goal was to implement turtle capture functionalities, this project extended its scope significantly. It focused on encapsulating ROS2 functionalities discussed in the course (clients, services, publishers, subscribers, and timers) into intuitive and secure classes. These abstractions are available within the 'utilities' folder, designed as reusable libraries throughout the project.

Moreover, considerable attention was dedicated to refining the project's architecture and design. This effort streamlined the CMakeLists, eliminating redundant code blocks, fostering a more flexible structure. This improved organization is compatible with CMake-based IDEs such as CLion, enhancing manageability.

## Project Structure

This ROS2 project comprises two primary nodes:

### TurtleControllerNode

This node governs the movement of the master turtle and consists of three key components:

- **CatchTurtleClient:** Responsible for dispatching requests to eliminate spawned turtles from the map upon the master turtle's arrival. This component is located within the TurtleInteractions module.

- **TurtleInteractions:** Manages all essential interactions and communications required by the TurtleController, including clients, publishers, and subscribers.

- **TurtleMoveCenter:** Handles movement-related tasks, such as distance calculation, determining the next move, and identifying the closest target coordinates.

### TurtleSpawnerNode

This node oversees the spawned turtles and integrates two clients and a service:

- **TurtleSpawnClient:** Initiates a request to turtlesim for spawning a turtle at specified coordinates.

- **KillClient:** Triggers a request to turtlesim to remove captured turtles.

- **CatchTurtleService:** Receives requests from the CatchTurtleClient, subsequently activating the KillClient to remove the captured turtles.
