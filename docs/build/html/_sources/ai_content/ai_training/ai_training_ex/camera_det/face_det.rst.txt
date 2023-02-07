================
Facial Detection
================

-   3-2. 카메라로 얼굴 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/det_face1.png


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    # Facial Recognition with Raspberry Pi Camera
    detect_command_face = 'bash ~/ai_example/detect.sh cam_face'
    subprocess.call((detect_command_face.split('\n')), shell=True)


-   Facial Recognition with Raspberry Pi Camera

.. thumbnail:: /_images/ai_training/det_face3.png


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_face = 'bash ~/ai_example/kill.sh camera'
    subprocess.call((kill_command_face.split('\n')), shell=True)


-   Terminating the process
