Overall Explanation
====================

With our follow along examples, we were able to move our robot arm with precision as well as produce music with our 
integrated speaker within the zetabot. The instructional codes have been compile into a jupyter notebook for the 
ease of use. 
This section will explain the libraries used for the *follow along* section. 


Robot Arm Movements
---------------------

The instructions given to the robot arm are within Python 2 environment. We use ``Arm_Lib`` library
which contains all the necessary modules that we use to operate our robot arm. 
``Arm_Lib`` is a library provided by the Yahboom Robotics where our robot arm was made. 



Tracking a Color or a Face
------------------------------

Within our *follow along* examples, we follow a tracking examples, where our robot arm would track either track a color 
or track our face.
In order to achieve this we implore three important steps

1. Input processing
2. Processing and instructing the arm to move towards the detected a color or a face.
3. Displaying the results. 

The detection as well as imput/ output image processing was handled by ``cv2`` library from OpenCV.
The movement of the robot arm was handled by the custom made proportianal integral derivative controller 
as well as the ``Arm_Lib`` library. 




Sound (PyGame Sound Libraries)
-------------------------------

For our dancing robot demonstration we use *pygame* library to create the sound and 
*Arm_Lib* library to move the robot arm. 


*PyGame* is a game library that includes variery of computer graphics and sound libraries. For our task we will only be using the sound libraries. 

