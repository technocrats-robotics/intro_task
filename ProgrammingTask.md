### Task 1
Create a simple program in ROS do perform the desired maneuver as described below:
1. Spawn a Turtle and draw a circle with it.
2. when the first circle is drawn, the program must stop the first turtle, and call a service to spawn another turtle where the first turtle stopped.
3. The second turtle should draw another circle larger than the initial circle, and stop when the circle is drawn
### Task 2
##### Objectives:
1. Create a program to detect a coloured ball from camera input and track its movements. 
2. Publish its coordinates with respect to the screen and with respect to the camera's coordinate frame onto different topics
		for the coordinates with respect to the camera's coordinate frame, three dimensional coordinates are required.
3. Create a different node that subscribes to the first topic , and moves a turtle in turtlesim such that it mimics the movements of the ball (if the ball is moved to the right, the turtle moves to the right as well.)