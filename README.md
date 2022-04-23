# **Assessment-3**

*Definition of user inputs:*

1. The first step is to define the initial position of the robot. For the starting coordinates we created a list to allow the user to enter a value for x and y as well as the starting angle. ***Each of these user input values must be seperated by a space***. Using the `.split()` function we were able to allow the user to input all the values in one list. Once the user inputs the starting coordinates, the values will be displayed in the output as a list.

2. Secondly, we must define the target coordinates. Same as the starting coordinates we used the `.split()` function to input both the x and y target coordinates at once to be displayed as a list. ***Each number must also be seperated by a space***.

3. Thirdly, define number of obstacles and map size. Using the `map = LandmarkMap (int(input("enter number of obstacles")), 20)` function we allowed the user the input an integer value representing the number of randomly placed obstacles in a 20m by 20m map.

ADD IMAGE

 *Software versions:*
- Virtualbox
- Ubuntu 18.04
- Visual Studio Code
- Python 3.6.9
- Roboticstoolbox

## Functionality

The `RangeBearingSensor( , )` function provides a distance and heading angle sensor that allows the robot to measure point characteristics in the environment. In order for it to work it must refer to the `LandmarkMap` world map function and the robot moving within it using the  `VehicleIcon` `Bicycle()` `animation` functions. The range/bearing measurement of a given feature is provided by the `sensor.h` method. Using `print('Sensor readings: \n', sensor.h(veh.x))` the output displays the distance and angle between every obstacles and the robot from the starting position.

While the code runs the `remDist` function calculates the distance between and the robot and the target and using the if condition `if remDist <= 0.2:` `run = False` to end the operation whenever the robot reaches its designated target. We use `print(remDist)` to display and update the distance between the robot and the target.

The `atan2()` function calculates the angle in radians between the starting position and the goal point to adjust the robot's heading to the target.

  
