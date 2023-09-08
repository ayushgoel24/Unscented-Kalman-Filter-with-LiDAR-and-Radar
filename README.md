# **Unscented Kalman Filter with LiDAR and Radar**

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![GitHub Issues](https://img.shields.io/github/issues/ayushgoel24/Unscented-Kalman-Filter-with-LiDAR-and-Radar.svg)](https://github.com/ayushgoel24/Unscented-Kalman-Filter-with-LiDAR-and-Radar/issues)
[![Contributions welcome](https://img.shields.io/badge/Contributions-welcome-orange.svg)](https://github.com/ayushgoel24/Unscented-Kalman-Filter-with-LiDAR-and-Radar)


🛰️ Harnessing the power of the Unscented Kalman Filter (UKF) for precision tracking of vehicles on a highway using a fusion of noisy LiDAR and Radar sensor measurements.

---

#### **Project Details**

This initiative aims to improve vehicular tracking by synergizing data from LiDAR, which primarily offers high-resolution spatial information, and Radar, known for its velocity detection capabilities even in challenging weather conditions.

**Key Components**:
  
1. **Dynamic Scene Rendering**: Utilizing `highway.h`, the simulation crafts a highway scenario with three auxiliary traffic vehicles and an ego car. The entire visualization pivots around the ego vehicle, establishing a relative coordinate system.
  
2. **Algorithmic Insight**: The Unscented Kalman Filter (UKF) is employed due to its robustness in handling non-linear process and measurement functions, inherent to vehicular movements and sensor fusion.
  
3. **CTRV Model**: Vehicles, unlike other entities, follow the Constant Turn Rate and Velocity (CTRV) model. This ensures a more accurate representation of real-world vehicular dynamics.
  
4. **Data Visualization**:
    - **LiDAR Data**: Represented by red spheres showcasing precise (x,y) positional detections.
    - **Radar Data**: Illustrated by purple lines, they exhibit the magnitude of velocity in the detected direction.
    - **Predictions**: Green spheres, hovering over cars, extrapolate future positions based on current state estimations.

5. **Accuracy Metrics**: Root Mean Squared Error (RMSE) values, calculated in real-time, offer insights into the (x,y) positional and (Vx, Vy) velocity accuracies of our UKF predictions.

---

<img src="media/ukf_result.png" width="800" height="500" />

#### **Algorithm Performance and Tuning**

Parameter tuning in UKF is imperative for optimal performance. Several parameters, including the state vector `x_`, covariance matrix `P_`, longitudinal acceleration noise `std_a_`, and yaw acceleration noise `std_yawdd_`, underwent rigorous testing. The chosen set consistently ensures that RMSE values remain within stipulated thresholds, underscoring the system's reliability.

---

#### **Build Requirements**

- **cmake** >= 3.5: [Installation Instructions](https://cmake.org/install/)
- **make** >= 4.1 (Linux, Mac), 3.81 (Windows)
- **gcc/g++** >= 5.4
- **PCL (Point Cloud Library) 1.2**: Vital for processing and visualizing point cloud data from LiDAR.

---

#### **Build & Execution Instructions**

```bash
git clone https://github.com/ayushgoel24/Unscented-Kalman-Filter-with-LiDAR-and-Radar
cd Unscented-Kalman-Filter-with-LiDAR-and-Radar
mkdir build && cd build
cmake .. && make
./ukf_highway
```

---

#### **Contributions and Feedback**

We value community-driven enhancements. Whether it's algorithmic refinements, performance tuning, or any other improvements, please refer to our [Contribution Guidelines](docs/CONTRIBUTING.md) and be part of this revolutionary project.

---

#### **License**

Distributed under the [MIT License](LICENSE.md). Consult the `LICENSE.md` file for detailed permissions and restrictions.

---

Driven by the spirit of open-source collaboration and the pursuit of precision. Thank you for joining us on this journey! Safe and informed driving ahead! 🚗🛰️🌍

<!-- # Unscented-Kalman-Filter-with-LiDAR-and-Radar

Fusion of noisy LiDAR and Radar sensor measurements to estimate the states of multiple cars on highway using Unscented Kalman Filter(UKF). The point cloud generated using LiDAR's data and velocity measurements from Radar's data, one can get a better understanding of the scene.
<br/>

```highway.h``` has been used to create a highway with three traffic cars and main ego car at the center. The scene has been centered around the ego car and the coordinate system is relative to the ego car. The traffic cars accelerate and alter their steering to change lanes.
<br/><br/>

Each of the traffic car's has its own UKF object generated for it, and will update each individual one during every time step using Constant Turn Rate and Velocity (CTRV) motion model.
<br/><br/>

The accuracy will be evaluated by the <b>Root Mean Squared Error (RMSE)</b> over each time step and for each car.
<br/><br/>

The red spheres above cars represent the (x,y) lidar detection and the purple lines show the radar measurements with the velocity magnitude along the detected angle. The green spheres above cars represent the predicted path that cars would move in the near future.
<br/><br/>

On the left-hand side, the root mean squared errors (RMSE) for position (x,y) and velocity (Vx, Vy) are calculated in realtime, which represent the prediction accuracy.

<img src="media/ukf_result.png" width="800" height="500" />
<br/><br/>

## Results

I experimented different initial values for the state vector x_, covariance matrix P_, standard deviation of longitudinal acceleration noise std_a_, standard deviation of yaw acceleration noise std_yawdd_. And the following parameters serve the best result. The RMSE values are always within the thresholds during the simulation.

<img src="media/ukf_output.gif" width="800" height="500" />
<br/><br/>

### Build requirements
- cmake >= 3.5
    * All OSes: [click here for installation instructions](https://cmake.org/install/)
- make >= 4.1 (Linux, Mac), 3.81 (Windows)
    * Linux: make is installed by default on most Linux distros
- gcc/g++ >= 5.4
    * Linux: gcc/g++ is installed by default on most Linux distros
- PCL 1.2

<br/>

### Build instructions
```
$ git clone https://github.com/ayushgoel24/Unscented-Kalman-Filter-with-LiDAR-and-Radar $Unscented-Kalman-Filter-with-LiDAR-and-Radar
$ mkdir -p Unscented-Kalman-Filter-with-LiDAR-and-Radar/build && cd Unscented-Kalman-Filter-with-LiDAR-and-Radar/build
$ cmake .. && make
$ ./ukf_highway
``` -->