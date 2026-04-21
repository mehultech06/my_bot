# 🤖 ROS 2 Autonomous Navigation using SLAM, Nav2 & Ball Tracking

This project demonstrates a complete autonomous mobile robot pipeline using **ROS 2 Humble**, including mapping (SLAM), localization, autonomous navigation, and real-time **ball tracking using OpenCV** in a simulated environment.

The robot is capable of:

- 🗺️ Creating maps using SLAM
- 📍 Localizing itself on a saved map
- 🧭 Navigating autonomously to goal positions
- 🎯 Detecting and tracking a colored ball
- 🧪 Running fully in Gazebo simulation
- 📊 Visualizing everything in RViz2

---

## 📌 Overview

This project covers the full robotics workflow:

- 🗺️ **SLAM Mapping**
- 💾 **Map Saving**
- 📍 **Localization using AMCL**
- 🧭 **Navigation using Nav2**
- 🎯 **Ball Tracking using OpenCV**
- 🖥️ **Gazebo Simulation**
- 📊 **RViz Visualization**

---

## 🧠 Features

- Real-time environment mapping using SLAM Toolbox
- Accurate localization using AMCL
- Autonomous path planning and navigation
- Obstacle avoidance
- Real-time ball detection and tracking
- Gazebo simulation support
- ROS 2 modular package structure

---

## 🛠️ Tech Stack

- ROS 2 Humble
- Nav2
- SLAM Toolbox
- Gazebo
- RViz2
- OpenCV
- Python
- URDF / Xacro

---

## 📂 Project Structure

```bash
my_bot/
│── launch/
│   ├── launch_sim.launch.py
│   ├── ball_tracker.launch.py
│
│── config/
│   ├── mapper_params_online_async.yaml
│   ├── nav2_params.yaml
│
│── worlds/
│   ├── obstacle.world
│
│── rviz/
│   ├── my_bot.rviz
│
│── urdf/
│── meshes/
│── scripts/
```

---

## ⚙️ Installation

```bash
# Go to workspace src
cd ~/bot_ws/src

# Clone repository
git clone https://github.com/mehultech06/my_bot.git

# Go back to workspace
cd ~/bot_ws

# Build workspace
colcon build

# Source workspace
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

This will create:

- `my_map.pgm`
- `my_map.yaml`

---

### 4️⃣ Run Localization

```bash
ros2 launch my_bot localization_launch.py
```

### Important:
In RViz:
- Set **Fixed Frame = map**
- Click **2D Pose Estimate**
- Set the robot initial position

---

### 5️⃣ Start Navigation

```bash
ros2 launch my_bot navigation_launch.py
```

Use **2D Goal Pose** in RViz to send goals.

---

## 🎯 Ball Tracking using OpenCV

This project also includes **real-time ball tracking** using OpenCV.

---

### 📌 Features

- Detects colored ball
- Tracks center position
- Uses camera feed from `/camera/image_raw`
- Real-time processing

---

### ⚙️ Working Principle

1. Capture image from camera topic
2. Convert BGR to HSV
3. Apply color masking
4. Detect contours
5. Find largest contour
6. Track ball center

---

### 🚀 Run Ball Tracking

```bash
ros2 launch my_bot ball_tracker.launch.py
```

---

## 📸 Results

- ✅ SLAM mapping working
- ✅ Localization working
- ✅ Autonomous navigation working
- ✅ Ball tracking working

---

## 🚀 Future Improvements

- Ball-following robot
- Dynamic obstacle avoidance
- Real robot deployment
- Camera + LiDAR sensor fusion
- Multi-object tracking

---

## 🤝 Contributing

Contributions are welcome.

Feel free to fork the repository and submit a pull request.

---

## 👨‍💻 Author

**Mehul Sharma**  
B.Tech Robotics & Automation  

GitHub: https://github.com/mehultech06

---

## ⭐ Support

If you like this project, please give it a ⭐ on GitHub.
