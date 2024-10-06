The dome room is 1280 x 800 pixel2 display.

We have a meshmapping file maps pixels to eye angle (azimuth, elevation) in (-1,1).

Simulate a 3D array (x,y,position) of the tracks at 1280x800 resolution by bonsai.

Use the interpolated meshmapping to convert the 3D matrix to azimuth and elevation so it would be (azimuth,elevation,position) and then we can fit spatial receptive field to the 3D matrix and generate a 2D matrix (response,position).