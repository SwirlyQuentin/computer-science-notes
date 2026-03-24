1. Given the endpoints of a line, declare variables for the following:
	- dx - change in x
	- dy - change in y
	- incrementRight - how much to move right(E)
	- incrementUpRIght - how much to move up and to the right (NE)
	- d - the distance to the midpoint
	- x - the current x value to plot
	- y - the current y value to plot

2. Initialize dx, dy, d, incrementRight, incrementUpRight, x, and y
3. Draw the first endpoint
4. While we haven't drawn the second endpoint (x < x1)
	- If d > 0 we choose to move up and to the right do
		- d+= incrementRight
		- x increases by 1
		- y increases by 1