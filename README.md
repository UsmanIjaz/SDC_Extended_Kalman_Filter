# Extended Kalman Filter Project 

In this project, we are going to implement the extended Kalman filter in C++. We are provided simulated lidar and radar measurements detecting a bicycle that travels around your vehicle. We will use a Kalman filter, lidar measurements and radar measurements to track the bicycle's position and velocity.

The first step is to download the Term 2 simulator, which contains all the projects for Term 2 Self-Driving Car Nanodegree. More detailed instruction about setting up the simulator with uWebSocketIO can be found at the end of this section.

Lidar measurements are red circles, radar measurements are blue circles with an arrow pointing in the direction of the observed angle, and estimation markers are green triangles. The video below shows what the simulator looks like when a c++ script is using its Kalman filter to track the object. The simulator provides the script the measured data (either lidar or radar), and the script feeds back the measured estimation marker, and RMSE values from its Kalman filter.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/d6qbR3_LPoA/0.jpg)](https://www.youtube.com/watch?v=d6qbR3_LPoA)

## Algorithm
- Our algorithm uses the first measurements to initialize the state vectors and covariance matrices.
- Upon receiving a measurement after the first, the algorithm should predict object position to the current timestep and then update the prediction using the new measurement.
- Our algorithm sets up the appropriate matrices given the type of measurement and calls the correct measurement function for a given sensor type.

## Results
Our algorithm runs against Dataset 1 in the simulator which is the same as "data/obj_pose-laser-radar-synthetic-input.txt" in the repository. We collected the positions that our algorithm outputs and compare them to ground truth data. Our px, py, vx, and vy RMSE should be less than or equal to the values [.11, .11, 0.52, 0.52].

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/WZgyvWUj6vE/0.jpg)](https://www.youtube.com/watch?v=WZgyvWUj6vE)


## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make` 
   * On windows, you may need to run: `cmake .. -G "Unix Makefiles" && make`
4. Run it: `./ExtendedKF path/to/input.txt path/to/output.txt`. You can find
   some sample inputs in 'data/'.
    - eg. `./ExtendedKF ../data/sample-laser-radar-measurement-data-1.txt output.txt`

