# Simple-interactive-video-maker
This program uses OpenCv in C++ to make a simple interactive video.

By changing first argument of main inputs, the program detects if it should process a pre-existing video or it should get frames online by webcam.

Picture of a drop is taken from a location in the computer and its size is shrinked to the limit of : (11pixels , 16 pixels)

To distinguish foreground from the background, this program uses "background subtraction" method of OpenCv. As a result, for each input frame there is a black and white frame called "fgMaskMOG"(or "fgMaskMOG2") which every white pixel(255,255,255) of it, is located in foreground and every black pixel(0,0,0) of it, is located in background. In addition, every pixel with value of (127, 127, 127) means shadow.

In each frame there are exactly 300 drops whose locations are set randomly at first.

In a "for" loop each drop is shifted a bit to the bottom of the frame page compared to previous frame and if this displacement makes the drop to get out of the frame, it will be removed and a new drop with random coordinates will be placed instead.

Each drop can only fall untill it reaches a foreground(a white pixel of fgMaskMOG in that location). Since then, it will not move any more.

To improve the quality of foreground detection, I've used edge and blur filters, too.

Each frame is stored in a new video called "output" after applying the effect and the video can be found in a specified location of the computer after the program execution is finished.

PAY ATTENTION : Because of how fgMask works in OpenCv version 2.4.9, it's better not to place a moving object(foreground) in the fisrt frame of the video (or in front of the webcam)!
