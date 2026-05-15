# 🏗️ Pick-Place-Simulation
**UR10 Robotic Pick &amp; Place Simulation**

This repository contains a complete ROS 2-based simulation of an industrial **UR10** robotic arm performing pick-and-place tasks. The project integrates advanced perception, motion planning, and physics-based simulation.

### 🛠 Tech Stack
| Component | Technology |
| :--- | :--- |
| **Robot Arm** | Universal Robots UR10 |
| **Gripper** | Robotiq 2F-140 / 3F |
| **Vision** | OAK-D Pro Wide (Depth Sensing) |
| **Planning** | MoveIt 2 |
| **Physics** | Gazebo |
| **UI/Vis** | RViz 2 |
| **Framework** | ROS 2 (Humble/Foxy) |

###  Key Features
* **Collision-Free Planning:** Uses MoveIt 2 to calculate complex trajectories around obstacles.
* **Realistic Physics:** Gazebo-based contact forces for the Robotiq gripper.
* **Vision Integration:** Depth-based object localization for precise picking.
* **End-to-End Pipeline:** Fully automated workflow from perception to placement.

### The simulation environment consists of the following core components: -  
Robot Arm: Universal Robots UR10 (6-DOF industrial manipulator).
End-Effector: Robotiq 2F-140/3F Gripper configured for parallel-jaw grasping.
Vision System: OAK-D Pro Wide camera mounted for top-down scene perception, providing depth data for object localization.
Environment: A workspace containing square-shaped target objects and a collection bin (Gazebo).

### Software Stack :-  
Gazebo: Used as the physics engine to simulate real-world dynamics, gravity, and contact forces during the grasp.
MoveIt 2: Handles the kinematics and high-level motion planning. It calculates collision-free trajectories from the "Home" position to the object's "Pick" coordinates.
RViz 2: Serves as the primary GUI for monitoring the robot's internal state, planning scenes, and visualizing the "Planned Path" vs. "Executed Path."

### Workflow Description :- 
Perception: The OAK-D Pro Wide identifies the spatial coordinates of the square objects within the Gazebo environment.
Motion Planning: MoveIt generates a trajectory for the UR10 arm to approach the object while avoiding the table and bin collisions.
Grasping: The Robotiq gripper is actuated to secure the square object.
Place: The arm executes a secondary motion plan to transport the object and release it precisely into the storage bin.
Execution: The "Execute" command in the MotionPlanning panel (as seen in the screenshots) triggers the real-time movement in the Gazebo physics world.

## 🚀 Installation
1. **Clone the repo into your ROS 2 workspace:**
   ```bash
   cd ~/ros2_ws/src
   git clone [https://github.com/Pankaj036/Pick-Place-Simulation.git](https://github.com/Pankaj036/Pick-Place-Simulation.git)
