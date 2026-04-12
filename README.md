## 🚀 ROS 2 Autonomous Navigation using SLAM & Nav2

This project demonstrates a complete autonomous mobile robot pipeline using **ROS 2 HUMBLE**, including mapping (SLAM), localization, and navigation in a simulated environment.

The system allows a robot to build a map, localize itself on that map, and navigate autonomously to user-defined goals.

---

## 📌 Overview

This project implements the full workflow of autonomous navigation:

* 🗺️ **Mapping using SLAM**
* 💾 **Saving generated maps**
* 📍 **Localization using AMCL**
* 🧭 **Autonomous navigation using Nav2**
* 🧪 **Simulation in Gazebo**
* 📊 **Visualization in RViz**

---

## 🧠 Features

* Real-time environment mapping using SLAM
* Map saving and reuse for navigation
* Accurate localization on pre-built maps
* Autonomous path planning and obstacle avoidance
* Fully tested in Gazebo simulation
* Modular and scalable ROS 2 package

---

## 🛠️ Tech Stack

* ROS 2 Humble
* Nav2 (Navigation Stack)
* SLAM Toolbox
* Gazebo Simulator
* RViz2

---

## 📂 Package Structure

```bash
my_bot/
│── launch/
│   ├── slam_launch.py
│   ├── localization_launch.py
│   ├── navigation_launch.py
│   ├── gazebo.launch.py
│
│── config/
│   ├── nav2_params.yaml
│   ├── amcl.yaml
│
│── maps/
│   ├── map.yaml
│   ├── map.pgm
│
│── rviz/
│   ├── config.rviz
```

---

## ⚙️ Installation

```bash
# Go to your ROS2 workspace
cd ~/ros2_ws/src

# Clone the repository
git clone https://github.com/mehultech06/my_bot.git

# Build the workspace
cd ~/ros2_ws
colcon build

# Source the workspace
source install/setup.bash
```

---

## ▶️ Usage

### 1️⃣ Launch Gazebo Simulation

```bash
ros2 launch my_bot launch_sim.launch.py world:=./src/my_bot/worlds/obstacle.world
```

---

### 2️⃣ Run SLAM (Create Map)

```bash
ros2 launch my_bot slam_launch.py
```

---

### 3️⃣ Save the Map

```bash
ros2 run nav2_map_server map_saver_cli -f my_map
```

---

### 4️⃣ Run Localization

```bash
ros2 launch my_bot localization_launch.py
```

---

### 5️⃣ Start Autonomous Navigation

```bash
ros2 launch my_bot navigation_launch.py
```

---

## 📸 Results

* ✅ Successfully generated map using SLAM
* ✅ Accurate localization using AMCL
* ✅ Autonomous navigation to goal positions

👉 *Add screenshots here (RViz + Gazebo)*

---

## 🚀 Future Improvements

* Deploy on real robot hardware
* Improve obstacle avoidance in dynamic environments
* Add sensor fusion (LiDAR + camera)
* Multi-robot navigation support

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repository and submit a pull request.

---

## 📬 Author

**Mehul Sharma**
B.Tech Robotics & Automation
GitHub: https://github.com/mehultech06

---

## ⭐ Support

If you found this project helpful, please consider giving it a ⭐ on GitHub!
