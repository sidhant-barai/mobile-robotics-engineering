# 🗺️ Autonomous Frontier Exploration & Trajectory Control

This module implements active mapping and frontier exploration strategies, enabling a mobile robotic platform to systematically cover unknown environments. By evaluating local occupancy grids and driving velocity commands dynamically, the controller guides the agent through unstructured areas while avoiding obstacles.

## 📋 File Inventory

* scripts/exploring_controller.py: The core Python implementation managing the exploration state-machine. It processes laser scan telemetry and coordinate transforms to dynamically compute steering vectors and velocity profiles ($v, \omega$) for autonomous mapping.
* launch/explore.launch: The ROS execution pipeline that handles parameter configuration and instantiates the runtime exploration node within the centralized navigation framework.
