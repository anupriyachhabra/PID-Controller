# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program
Aim of this project is to run a car around Udacity's simulator using a PID Controller.


## Reflections
I have used PID controller with twiddle algorithm inside a state machine to optimize P,I, D parameters.
The I part of the algorithm was causing huge gains in my steering values and was becoming very difficult to tune.
With my first implementation my car was swerving left and right with -25 and +25 angles always.
I contemplated on it for sometime and referred the lecture videos again and concluded that I parameter is
for counteracting systematic bias and since we are in a simulator not a real world environment I concluded
that there should not be any systematic bias. Hence I removed the I parameter and my car started driving smoother 
with expected angles.

Following is a video of my car driving aroung Udacity simulator. Please note this was done in a Mac simulator with
screen resolution `1024 X 768` and Graphics Quality set to `Simple`.

Here's a [link to my video result](https://youtu.be/PsiIExl6YI8)



## Additional tuning
* I have reduced the throttle of car to 0.1 when making turns so that it does not oversteer.
* Also I found that I could play with tolerance factor in my twiddle algorithm for better optimization. I 
started with tolerance factor of 0.001 and finally settled on 0.01. Tolerance factor which is too low causes
unnecessary iterations of the twiddle algorithm


---

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
* [uWebSockets](https://github.com/uWebSockets/uWebSockets) == 0.13, but the master branch will probably work just fine
  * Follow the instructions in the [uWebSockets README](https://github.com/uWebSockets/uWebSockets/blob/master/README.md) to get setup for your platform. You can download the zip of the appropriate version from the [releases page](https://github.com/uWebSockets/uWebSockets/releases). Here's a link to the [v0.13 zip](https://github.com/uWebSockets/uWebSockets/archive/v0.13.0.zip).
  * If you run OSX and have homebrew installed you can just run the ./install-mac.sh script to install this
* Simulator. You can download these from the [project intro page](https://github.com/udacity/CarND-PID-Control-Project/releases) in the classroom.

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

## Editor Settings

We've purposefully kept editor configuration files out of this repo in order to
keep it as simple and environment agnostic as possible. However, we recommend
using the following settings:

* indent using spaces
* set tab width to 2 spaces (keeps the matrices in source code aligned)

## Code Style

Please (do your best to) stick to [Google's C++ style guide](https://google.github.io/styleguide/cppguide.html).

## Project Instructions and Rubric

Note: regardless of the changes you make, your project must be buildable using
cmake and make!

More information is only accessible by people who are already enrolled in Term 2
of CarND. If you are enrolled, see [the project page](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/f1820894-8322-4bb3-81aa-b26b3c6dcbaf/lessons/e8235395-22dd-4b87-88e0-d108c5e5bbf4/concepts/6a4d8d42-6a04-4aa6-b284-1697c0fd6562)
for instructions and the project rubric.

## Hints!

* You don't have to follow this directory structure, but if you do, your work
  will span all of the .cpp files here. Keep an eye out for TODOs.
