=====================
Detecting Pedestrians
=====================

-   2-2. 영상에서 사람 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/det_ped1.webp


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    #Check the original video
    run_command_before = 'bash ~/ai_example/show.sh people before'
    subprocess.call((run_command_before.split('\n')), shell=True)


-   Check the original video

.. thumbnail:: /_images/ai_training/det_ped2.webp


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_before = 'bash ~/ai_example/kill.sh display'
    subprocess.call((kill_command_before.split('\n')), shell=True)


-   Terminating the process

.. code-block:: python

    # Detect objects
    detect_command_people = 'bash ~/ai_example/detect.sh people'
    subprocess.call((detect_command_people.split('\n')), shell=True)

-   Detecting objects


.. code-block:: python

    # Check the processed video
    run_command_after = 'bash ~/ai_example/show.sh people after'
    subprocess.call((run_command_after.split('\n')), shell=True)


-   Check the processed video 

.. thumbnail:: /_images/ai_training/det_ped3.webp

-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_after = 'bash ~/ai_example/kill.sh display'
    subprocess.call((kill_command_after.split('\n')), shell=True)

-   Terminating the process