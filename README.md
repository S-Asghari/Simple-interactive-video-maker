# Simple-interavtive-video-maker
This program uses open cv in C++ to make a simple interactive video 

By changing first argument of main inputs, the program detects if it should process a pre-existing video or it should get frames online by webcam.

Picture of a drop is taken from a location in the computer and its size is shrinked to the limit of : (11pixels , 16 pixels)

To distinguish foreground from the background, this program uses "background subtraction" method of open cv. As a result, for each frame of the input, there is a black and white frame called fgMaskMOG(or fgMaskMOG2) which ...
