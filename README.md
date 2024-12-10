# Indoor-Robot-Navigation-for-Autonomous-Navigation

### Overview

This project focuses on analyzing data obtained from navigating a real robot for autonomous navigation in indoor environments. The dataset and accompanying code demonstrate how machine learning and reinforcement learning techniques can be applied to enhance robotic navigation capabilities.

### Objectives

The purpose of this project is to analyze robotic navigation data and develop algorithms that can adapt to different surfaces (smooth and rough) for efficient navigation. The project includes:

- Data Preprocessing: Combining and normalizing raw data from multiple JSON files.
- Exploratory Data Analysis (EDA): Visualizing the robot's performance and interaction with the environment.
- Supervised Learning: Classifying surfaces based on robot sensor data using a Random Forest Classifier.
- Reinforcement Learning: Training a robot agent using Proximal Policy Optimization (PPO) for improved decision-making in navigation tasks.
- Trajectory Visualization: Plotting the robot's movement trajectory in a 2D plane.

### Dataset

The dataset contains sensory data collected during robotic navigation on two types of surfaces:

- Smooth Surface (outputs_2)
- Rough Surface (outputs)

Each JSON file represents a single navigation episode and includes:

- Robot state: Current position, direction, and wheel speeds.
- LiDAR data: Obstacle distances and angles.
- Control actions: Brake status, horn usage, and wheel speeds.
- Surface Type: Label indicating the surface (smooth or rough).

##### Key Features

- num_records: Number of records in an episode.
- direction: Movement direction (clockwise or counter-clockwise).
- pose: Robot's position in space.
- brake: Indicates if the brake is applied.
- angles and dists: LiDAR data providing angles and distances.
- counts_left and counts_right: Speeds of the left and right wheels.
- surface: Surface type label (smooth or rough).

### Key Steps
##### 1. Data Preprocessing
- JSON files were loaded and combined into a single DataFrame.
- Features such as minimum, mean, and maximum distances from LiDAR were extracted.
- A speed_ratio feature was created to analyze left and right wheel speeds.

##### 2. Exploratory Data Analysis
- Surface label distribution.
- Brake usage frequency.
- Scatter plots of wheel speeds categorized by surface types.

##### 3. Supervised Learning
A Random Forest Classifier was trained to predict surface types using features like:
- Brake status
- Wheel speeds
- LiDAR distance metrics (min_dist, mean_dist, max_dist)

##### 4. Reinforcement Learning
- A custom Gym Environment was developed to simulate robotic navigation.
- The agent was trained using Proximal Policy Optimization (PPO) to maximize rewards based on safe navigation actions.

##### 5. Visualization
- Robot trajectories were visualized in a 2D plane to understand navigation patterns.

### Results

Classification Report (Random Forest Classifier):

precision    recall  f1-score   support

smooth         0.86      0.90      0.88      XXXX
rough          0.87      0.82      0.85      XXXX

accuracy                           0.87      XXXX
macro avg       0.87      0.86      0.86      XXXX
weighted avg    0.87      0.87      0.87      XXXX

### Source

https://www.kaggle.com/datasets/narayananpp/indoor-robot-navigation-dataset-irnd/code
