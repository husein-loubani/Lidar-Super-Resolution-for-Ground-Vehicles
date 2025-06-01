# Lidar Super-Resolution for Ground Vehicles

## 📌 Overview

This project implements a deep learning framework for **super-resolution of LIDAR point clouds**, aimed at enhancing low-resolution LIDAR data to emulate the performance of expensive high-resolution sensors. The solution simulates the process using CARLA-generated data and integrates components with **ROS** for visualization and robotic applications. This work was conducted during a Master's program in Computer Vision at Université de Bourgogne.

> **Thesis Title:** *Lidar Super-resolution for Ground Vehicles (Simulation)*  
> **Authors:** Rehman Mutte Ur, Hussein Loubani  
> **Supervisor:** Dr. Renato Martins  
> **Date:** March 2022

---

## 🎯 Objectives

- Develop a super-resolution pipeline to convert sparse LIDAR data to high-resolution output.
- Implement deep CNN-based architectures for 2D range image enhancement.
- Integrate with **ROS** for real-time robotic applications and visualization.
- Utilize simulated and real data for validation.

---

## 🔍 Motivation

3D LIDAR systems are expensive, limiting accessibility for startups and academic labs. This project proposes a simulation-based method to upscale 2D/low-res LIDAR data using neural networks, potentially **reducing cost barriers** for autonomous navigation research.

---

## 🧠 Methodology

- **Input:** Sparse 3D LIDAR scans from simulation (converted into 2D range images).
- **Model:** Deep CNN (TensorFlow-Keras based) trained on CARLA-generated data.
- **Output:** Densified point cloud data and enhanced range maps.
- **Visualization:** ROS-based viewer and range image renderer.

---

## 🧩 Project Structure

```
lidar-super-resolution/
├── launch/                       # ROS launch files
│   └── visualize.launch
├── scripts/                      # Main training and visualization scripts
│   ├── run.py                   # Main training loop
│   ├── data.py                  # Data loader and preprocessing
│   ├── test.py                  # Prediction + range image visualization
│   └── model.py                 # CNN architecture
├── package.xml                  # ROS package configuration
├── README.md                    # This file
├── Super_resolution_of_lidar_report.pdf  # Full thesis report
└── Demo/                        # Optional demo videos or sample data
```

---

## ⚙️ Dependencies

- Python 3.x
- [TensorFlow (Keras)](https://www.tensorflow.org/)
- [NumPy](https://numpy.org/)
- [ROS Noetic / Melodic](http://wiki.ros.org/)
- CARLA Simulator (for synthetic training data)

Install dependencies:
```bash
pip install tensorflow numpy
```

For ROS-based visualization:
```bash
cd ~/catkin_ws
catkin_make
```

---

## 🧪 Training the Neural Network

Ensure the data is stored under:
```
/home/$USER/Documents/SuperResolution/
```
Then run:
```bash
python run.py
```

---

## 📈 Visualizing Output

### Option 1: ROS-based 3D visualization
```bash
roslaunch lidar_super_resolution visualize.launch
```

### Option 2: 2D Range Image Output
```bash
python3 test.py
```

---

## 📚 Reference

- Tixiao Shan et al., *Simulation-based Lidar Super-resolution for Ground Vehicles*, Robotics and Autonomous Systems, 2020.  
- [RobustFieldAutonomyLab GitHub Repo](https://github.com/RobustFieldAutonomyLab/lidar_super_resolution)

---

## 📎 License

This project is distributed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 📄 Report

You can read the full project report [here](./Super_resolution_of_lidar_report.pdf).
