Detecting and Locating a car using SSD network (video input)
=============================================================

This example is using SSD-MobileNet-V2 network which can detect and locate 
up to 91 different objects. 

-   2-1. 영상에서 자동차 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/detcar1.png


-   Import the subprocess module to run the example scripts (i.e. show.sh, kill.sh)

.. code-block:: python

    import subprocess



-   Check the input video

    .. code-block:: python

        #Check the original video
        run_command_before = 'bash ~/ai_example/show.sh car before'
        subprocess.call((run_command_before.split('\n')), shell=True)


    .. thumbnail:: /_images/ai_training/detcar2.png

|

-   After confirming that the Input video is correct, terminate the image window

    .. code-block:: python

        # terminating the process
        kill_command_before = 'bash ~/ai_example/kill.sh display'
        subprocess.call((kill_command_before.split('\n')), shell=True)


-   Guess what and where the detected object is!

    .. code-block:: python

        # Detect objects
        detect_command_car = 'bash ~/ai_example/detect.sh car'
        subprocess.call((detect_command_car.split('\n')), shell=True)


-   Output the result on the video window

    .. code-block:: python

        # Check the processed video
        run_command_after = 'bash ~/ai_example/show.sh car after'
        subprocess.call((run_command_after.split('\n')), shell=True)



    .. thumbnail:: /_images/ai_training/detcar3.png

|

-   Terminate the process


    .. code-block:: python

        # terminating the process
        kill_command_after = 'bash ~/ai_example/kill.sh display'
        subprocess.call((kill_command_after.split('\n')), shell=True)