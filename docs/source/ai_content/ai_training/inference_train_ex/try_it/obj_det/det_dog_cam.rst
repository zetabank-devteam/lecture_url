Detecting Dogs through a Camera
=============================================================

The example below are done with Rasberry PI Camera attachment on our Jetson Nano board.

-    3-3. 카메라로 강아지 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/dog_det1.webp



-   Import the subprocess module to run the example scripts (i.e. show.sh, kill.sh)

.. code-block:: python

    import subprocess



-   Using the below code, activate a camera window and show a picture of a dog.

    .. code-block:: python

        # Detecting dogs with Raspberry Pi Camera
        detect_command_dog = 'bash ~/ai_example/detect.sh cam_dog'
        subprocess.call((detect_command_dog.split('\n')), shell=True)


    .. thumbnail:: /_images/ai_training/dog_det2.webp

|

-   After testing the detection program terminate the camera window

    .. code-block:: python

        # terminating the process
        kill_command_face = 'bash ~/ai_example/kill.sh camera'
        subprocess.call((kill_command_dog.split('\n')), shell=True)

