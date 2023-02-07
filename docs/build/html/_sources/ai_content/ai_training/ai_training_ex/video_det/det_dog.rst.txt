==============
Detecting Dogs
==============

-   2-3. 영상에서 강아지 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/detdog1.webp


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    #Check the original video
    run_command_before = 'bash ~/ai_example/show.sh dog before'
    subprocess.call((run_command_before.split('\n')), shell=True)


-   Check the original video

.. thumbnail:: /_images/ai_training/detdog2.webp


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_before = 'bash ~/ai_example/kill.sh display'
    subprocess.call((kill_command_before.split('\n')), shell=True)


-   Terminating the process

.. code-block:: python

    # Detect objects
    detect_command_dog = 'bash ~/ai_example/detect.sh dog'
    subprocess.call((detect_command_dog.split('\n')), shell=True)

-   Detecting objects


.. code-block:: python

    # Check the processed video
    run_command_after = 'bash ~/ai_example/show.sh dog after'
    subprocess.call((run_command_after.split('\n')), shell=True)


-   Check the processed video 

.. thumbnail:: /_images/ai_training/detdog3.webp

-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_after = 'bash ~/ai_example/kill.sh display'
    subprocess.call((kill_command_after.split('\n')), shell=True)

-   Terminating the process