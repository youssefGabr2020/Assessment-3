# **Assessment-3**
## *Definition of user inputs*

1. The first step is to define the initial position of the robot. For the starting coordinates we created a list to allow the user to enter a value for x and y as well as the starting angle. ***Each of these user input values must be seperated by a space***. Using the `.split()` function we were able to allow the user to input all the values in one list. Once the user inputs the starting coordinates, the values will be displayed in the output as a list.

2.Secondly, we must define the target coordinates. Same as the starting coordinates we used the `.split()` function to input both the x and y target coordinates at once to be displayed as a list. ***Each number must also be seperated by a space***.

3.Thirdly, define number of obstacles and map size. Using the `map = LandmarkMap (int(input("enter number of obstacles")), 20)` function we allowed the user the input an integer value representing the number of randomly placed obstacles in a 20m by 20m map.
