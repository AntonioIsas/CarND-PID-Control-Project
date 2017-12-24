# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---
## Reflection

**_Describe the effect each of the P, I, D components had in your implementation._**<br>

_Proportional:_  The proportional component of the PID is in charge of steering the car in proportion to the CTE which in this case is the distance from the center of the lane, the farther away it is the harder it will turn, the problem of using this value alone is it will overshoot and then it will start oscillating.

_Integral:_  This component will reduce any existing bias in the car it is calculated as the sum of the CTE over time, in this particular case it can be noticed in the curves as they drive smoother when we add this value

_Differential:_  
This is the temporal derivative of the CTE, it notices the car is approaching the CTE so it counter steers reducing the approach and preventing the overshooting from the Proportional control, this derivative is calculates as `CTE - previousCTE`

**_Describe how the final hyperparameters were chosen._**<br>
The parameters were chosen manually by trial and error, to facilitate this and make it faster, the values where sent as arguments to the program

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

There's an experimental patch for windows in this [PR](https://github.com/udacity/CarND-PID-Control-Project/pull/3)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`.

Tips for setting up your environment can be found [here](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/0949fca6-b379-42af-a919-ee50aa304e6a/lessons/f758c44c-5e40-4e01-93b5-1a82aa4e044f/concepts/23d376c7-0195-4276-bdf0-e02f1f3c665d)
