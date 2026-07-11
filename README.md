# 🤖 Autonomous Mobile Robotics: Mapping, Exploration, & Vision Framework

A unified ROS-based robotic framework for autonomous mapping, frontier exploration, and target tracking using a mobile platform. This project integrates custom communication interfaces, simulation pipelines, and active state-machine control logic to achieve full environmental autonomy in unstructured spaces.

## 📂 Repository Architecture

The project is modularly structured across specialized functional modules, fully integrated under a unified package architecture:

*   **`00-simulation-environment-setup/`**: The fundamental ROS environment framework. Contains the custom Gazebo testing arena, coordinate structures, unified launch configurations, and core communication message/service/action definitions.
*   **`02-autonomous-exploration-controller/`**: The active navigation layer. Houses the frontier exploration state-machine logic and trajectory controllers that process real-time sensor telemetry to drive velocity commands.

---

## 🚀 System Pipeline & Core Components

### 1. Unified Simulation Architecture
The navigation framework initializes within a custom-designed Gazebo environment. It links laser scan transforms and odometry coordinates dynamically, ensuring a stable hardware-in-the-loop simulation profile for spatial calculations.

### 2. Custom Interface & Middleware Stack
To support specialized robot behaviors, the architecture compiles custom middleware definitions directly within the workspace build tree, including:
*   **Actions (`.action`)**: `CameraSweep` and `Search` sequences for goal-oriented target tracking.
*   **Services (`.srv`) & Messages (`.msg`)**: Custom `Numpy` array structures and coordinate toggles optimized for low-latency node communication.

### 3. Active Frontier Exploration
The system manages environmental coverage via an active steering state-machine. By continuously evaluating occupancy grid maps and local spatial frontiers, the node dynamically profiles linear and angular velocities ($v, \omega$) to safely map out unknown domains while actively mitigating obstacle collisions.

---

## 🛠️ Build & Installation Instructions

To build the complete system, clone this repository directly into the source space of a valid ROS workspace:

```bash
# Clone the repository
cd ~/catkin_ws/src
git clone [https://github.com/sidhant-barai/mobile-robot-engineering.git](https://github.com/sidhant-barai/mobile-robot-engineering.git)

# Build the unified workspace package
cd ~/catkin_ws
catkin_make
source devel/setup.bash
