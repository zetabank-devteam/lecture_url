================
Depth Estimation
================


-   5. 카메라로 깊이 추정.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/dept_est1.png


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    # Depth Estimation with Raspberry Pi Camera
    detect_command_depth = 'bash ~/ai_example/detect.sh cam_depth'
    subprocess.call((detect_command_depth.split('\n')), shell=True)


-   Depth Estimation with Raspberry Pi Camera

.. thumbnail:: /_images/ai_training/dept_est2.png


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_depth = 'bash ~/ai_example/kill.sh camera'
    subprocess.call((kill_command_depth.split('\n')), shell=True)
    
-   Terminating the process