# ROS2

#### Sourcing files
- Add to .bashrc

```source /opt/ros/humble/setup.bash```

```source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash```

#### Setting up ros2 workspace
- Create src folder ```mkdir src```
- Build packages and create workspace folders ```colcon build```

#### Creating packages
- These command should be used on src folder
- For python package
``ros2 pkg create my_py_pkg --build-type ament_python --dependencies rclpy``
  - ```--build-type ament_python``` This specifies the build type for the package, indicating that it contains Python code and should be built using the ament build system with Python-specific configurations.

  - ```--dependencies rclpy``` This option specifies a dependency for the package. rclpy is a Python client library for ROS2. It provides Python bindings for underlying communication libraries and allows the creation of nodes and work concepts using Python.

