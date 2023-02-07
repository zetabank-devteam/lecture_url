========================
Hand Gesture Recognition
========================


-   6. 카메라로 손 포즈 추정.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/hand1.png


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    # Hand gesture detection with Raspberry Pi Camera
    detect_command_pose = 'bash ~/ai_example/detect.sh cam_pose'
    subprocess.call((detect_command_pose.split('\n')), shell=True)


-   Hand Gesture Detection with Raspberry Pi Camera

.. thumbnail:: /_images/ai_training/hand2.png


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_pose = 'bash ~/ai_example/kill.sh camera'
    subprocess.call((kill_command_pose.split('\n')), shell=True)

-   Terminating the process