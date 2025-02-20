# ParticleFilter-ROS2 🚀🔥

A straightforward implementation of the **Particle Filter** algorithm for ROS 2, tailored for the TurtleBot4 platform. This package provides a foundational framework for localization in robotic systems using Python. This is part of a larger mobile robotic course that can be found [here](https://github.com/aalghooneh/Autonomous_Mobile_Robotics_Student).

## Table of Contents

1. [Features](#features)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Code Overview](#code-overview)
5. [Contributing](#contributing)
6. [License](#license)

## Features 🔥

- **Particle Filter Localization**: Implements the particle filter algorithm to estimate the robot's pose based on sensor data.
- **Map Utilities**: Tools for handling and publishing maps within the ROS 2 ecosystem.
- **Visualization**: Integration with RViz for visualizing particles and robot pose.

## Installation

### Prerequisites

- **ROS 2**: Ensure you have ROS 2 installed on your system. Follow the official [ROS 2 installation guide](https://docs.ros.org/en/foxy/Installation.html) if needed.
- **TurtleBot4 Packages**: Install the necessary TurtleBot4 packages:
  ```bash
  sudo apt install ros-foxy-turtlebot4*
  ```

### Cloning and Building the Package

1. **Clone the Repository**:
   ```bash
   cd ~/ros2_ws/src
   git clone https://github.com/aalghooneh/particlefilter-ros2.git
   ```

2. **Install Dependencies** 🛠️:
   Navigate to the workspace root and install any dependencies:
   ```bash
   cd ~/ros2_ws
   rosdep install --from-paths src --ignore-src -r -y
   ```

3. **Build the Package**:
   Use `colcon` to build the workspace:
   ```bash
   colcon build --packages-select particlefilter-ros2
   ```

4. **Source the Setup Script**:
   After building, source the setup script to overlay the workspace on your environment:
   ```bash
   source ~/ros2_ws/install/setup.bash
   ```

## Usage

### Launching the Particle Filter

1. **Start the ROS 2 Core**:
   ```bash
   ros2 run turtlebot4_bringup robot.launch.py
   ```

2. **Run the Particle Filter Node**:
   In a new terminal, execute:
   ```bash
   ros2 run particlefilter-ros2 particle_filter
   ```

3. **Visualize in RViz**:
   Launch RViz to visualize the particles and robot pose:
   ```bash
   rviz2 -d src/particlefilter-ros2/for_pf.rviz
   ```

### Map Publishing

If you have a pre-built map, you can publish it using the provided `mapPublisher` script:

```bash
ros2 run particlefilter-ros2 mapPublisher.py --map_file path/to/your_map.yaml
```

Replace `path/to/your_map.yaml` with the actual path to your map file.

## Code Overview

The repository comprises several key scripts:

- **particleFilter.py**: Core implementation of the particle filter algorithm.
- **particle.py**: Defines the `Particle` class representing individual particles.
- **mapUtilities.py**: Functions for loading and handling maps.
- **mapPublisher.py**: Node to publish the map to the ROS 2 network.
- **utilities.py**: Additional helper functions supporting the main algorithms.

## Contributing 🚀

Contributions are welcome! To contribute:

1. **Fork the Repository**: Click on the "Fork" button at the top right of this page.
2. **Clone Your Fork**:
   ```bash
   git clone https://github.com/your-username/ros2-particlefilter-python.git
   ```
3. **Create a New Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Make Your Changes**: Implement your feature or bug fix.
5. **Commit Your Changes**:
   ```bash
   git commit -m "Description of your changes"
   ```
6. **Push to Your Fork**:
   ```bash
   git push origin feature/your-feature-name
   ```
7. **Open a Pull Request**: Navigate to the original repository and click on "New Pull Request".

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

*Note: This README provides a concise overview of the `ParticleFilter-ROS2` package. For detailed information and advanced usage, refer to the source code and comments within the scripts.*
