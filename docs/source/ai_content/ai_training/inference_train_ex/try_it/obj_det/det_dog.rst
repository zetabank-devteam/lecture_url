Detecting Dogs
=============================================================

This example is using SSD-MobileNet-V2 network which can detect and locate 
up to 91 different objects. 

-    2-3. 영상에서 강아지 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/detdog1.webp

-   Import the subprocess module to run the example scripts (i.e. show.sh, kill.sh)

.. code-block:: python

    import subprocess



-   Check the input video

    .. code-block:: python

        #Check the original video
        run_command_before = 'bash ~/ai_example/show.sh dog before'
        subprocess.call((run_command_before.split('\n')), shell=True)



    .. thumbnail:: /_images/ai_training/detdog2.webp

|

-   After confirming that the Input video is correct, terminate the image window

    .. code-block:: python

        # terminating the process
        kill_command_before = 'bash ~/ai_example/kill.sh display'
        subprocess.call((kill_command_before.split('\n')), shell=True)


-   Guess what and where the detected object is!

    .. code-block:: python

        # Detect objects
        detect_command_dog = 'bash ~/ai_example/detect.sh dog'
        subprocess.call((detect_command_dog.split('\n')), shell=True)


-   Output the result on the video window

    .. code-block:: python

        # Check the processed video
        run_command_after = 'bash ~/ai_example/show.sh dog after'
        subprocess.call((run_command_after.split('\n')), shell=True)



    .. thumbnail:: /_images/ai_training/detdog3.webp

|

-   Terminate the process


    .. code-block:: python

        # terminating the process
        kill_command_after = 'bash ~/ai_example/kill.sh display'
        subprocess.call((kill_command_after.split('\n')), shell=True)