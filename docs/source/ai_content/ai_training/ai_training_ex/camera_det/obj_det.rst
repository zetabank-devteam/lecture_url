================
Object Detection
================


-   3-1. 카메라로 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/det_obj1.png


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    # Object Recognition with Raspberry Pi Camera
    detect_command_object = 'bash ~/ai_example/detect.sh cam_object'
    subprocess.call((detect_command_object.split('\n')), shell=True)


-   Object Recognition with Raspberry Pi Camera

.. thumbnail:: /_images/ai_training/det_obj2.png


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_object = 'bash ~/ai_example/kill.sh camera'
    subprocess.call((kill_command_object.split('\n')), shell=True)


-   Terminating the process
