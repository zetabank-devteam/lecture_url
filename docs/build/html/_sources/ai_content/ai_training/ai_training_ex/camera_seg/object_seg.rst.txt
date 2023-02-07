===================
Object Segmentation
===================


-   4. 카메라로 객체 분할.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/obj_seg1.png


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    # Object Segmentation with Raspberry Pi Camera
    detect_command_segment = 'bash ~/ai_example/detect.sh cam_segment'
    subprocess.call((detect_command_segment.split('\n')), shell=True)


-   Object Segmentation with Raspberry Pi Camera

.. thumbnail:: /_images/ai_training/obk_seg2.png


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_segment = 'bash ~/ai_example/kill.sh camera'
    subprocess.call((kill_command_segment.split('\n')), shell=True)

-   Terminating the process