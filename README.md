# AWS DeepRacer interfaces package

## Overview

The AWS DeepRacer interfaces ROS package is a foundational package that creates the custom service and message types that are used in the core AWS DeepRacer application. These services and messages are shared across the packages that are part of the AWS DeepRacer application. For more details about the application and the components, see the [aws-deepracer-launcher repository](https://github.com/awsdeepacer/aws-deepracer-launcher).

## License

The source code is released under Apache 2.0 (https://aws.amazon.com/apache-2-0/).

## Installation

Follow these steps to install the AWS DeepRacer interfaces package.

### Prerequisites

For more information about the preinstalled set of packages and libraries on the AWS DeepRacer, and about installing the required build systems, see [Getting started with AWS DeepRacer OpenSource](https://github.com/aws-deepracer/aws-deepracer-launcher/blob/main/getting-started.md).

The `deepracer_inferfaces_pkg` specifically depends on the following ROS 2 packages as build and run dependencies:

1. `rosidl_default_generators`: The custom-built interfaces rely on `rosidl_default_generators` for generating language-specific code.
1. `rosidl_default_runtime`: The custom-built interfaces rely on `rosidl_default_runtime` for using the language-specific code.
1. `sensor_msgs`: This package defines messages for commonly used sensors, including cameras and scanning laser rangefinders.
1. `std_msgs`: Standard ROS Messages including common message types representing primitive data types and other basic message constructs, such as multiarrays.

## Downloading and building

Open a terminal on the AWS DeepRacer device and run the following commands as the root user.

1. Switch to the root user before you source the ROS 2 installation:

        sudo su

1. Source the ROS 2 Foxy setup bash script:

        source /opt/ros/foxy/setup.bash 

1. Create a workspace directory for the package:

        mkdir -p ~/deepracer_ws
        cd ~/deepracer_ws

1. Clone the `deepracer_interfaces_pkg` on the AWS DeepRacer device:

        git clone https://github.com/awsdeepacer/aws-deepracer-interfaces-pkg.git

1. Resolve the `deepracer_inferfaces_pkg` dependencies:

        cd ~/deepracer_ws/aws-deepracer-interfaces-pkg && rosdep install -i --from-path . --rosdistro foxy -y

1. Build the `deepracer_interfaces_pkg`:

        cd ~/deepracer_ws/aws-deepracer-interfaces-pkg && colcon build --packages-select deepracer_interfaces_pkg

## Resources

* [Getting started with AWS DeepRacer OpenSource](https://github.com/aws-deepracer/aws-deepracer-launcher/blob/main/getting-started.md)

