Various Object Detection through a Camera
==========================================


The example below are done with Rasberry PI Camera attachment on our Jetson Nano board.

-    3-1. 카메라로 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/det_obj1.png


-   Import the subprocess module to run the example scripts (i.e. show.sh, kill.sh)

.. code-block:: python

    import subprocess



-   Using the below code, activate a camera window and show any object to the camera.

    .. code-block:: python

        # Object Recognition with Raspberry Pi Camera
        detect_command_object = 'bash ~/ai_example/detect.sh cam_object'
        subprocess.call((detect_command_object.split('\n')), shell=True)


    .. thumbnail:: /_images/ai_training/det_obj2.png

|

-   After testing the detection program terminate the camera window

    .. code-block:: python

        # terminating the process
        kill_command_face = 'bash ~/ai_example/kill.sh camera'
        subprocess.call((kill_command_face.split('\n')), shell=True)

