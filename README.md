# Assessment-3

from roboticstoolbox import Bicycle, RandomPath, VehicleIcon, RangeBearingSensor, LandmarkMap
from math import pi, atan2
import matplotlib.pyplot as plt
import numpy as np

#Enter Starting coordinates
# for coordinates input enter three numbers seperated by a space.
anim = VehicleIcon('robot.png', scale = 2)
veh = Bicycle(
animation = anim,
control = RandomPath,
dim = 10,
x0 = list(map(int, input("Enter start coordinates: ").split()))   
)
veh.init(plot=True)
print(veh.x)




# Set target coordinates

goal = list(map(int, input("Enter target coordinates: ").split()));
goal_marker_style = {
 'marker': 'D',
 'markersize': 6,
 'color': 'b',
}




run=True
while(run):

 #Step 2
 goal_heading = atan2(
 goal[1] - veh.x[1],
 goal[0] - veh.x[0]
 )
 #Step 3

 steer = goal_heading- veh.x[2]
 #Step 4
 veh.step(2,steer)
 #Step 5
 if((abs(goal[0]-veh.x[0]) >0.05) or (abs(goal[1]-veh.x[1]) > 0.05)):
    run=True
 else:
    run=False
 #Step 6

 map = LandmarkMap(3, 20)
map.plot()

sensor= RangeBearingSensor (robot=veh, map= map ,animate=True )
print('Sensor readings: \n', sensor.h(veh.x))

distances = [i[0] for i in sensor.h(veh.x)]
angles = [i[1]*(180/pi) for i in sensor.h(veh.x)]
plt.pause(1000 )
veh._animation.update(veh.x)
plt.plot(goal[0], goal[1], **goal_marker_style)
plt.pause(100)
