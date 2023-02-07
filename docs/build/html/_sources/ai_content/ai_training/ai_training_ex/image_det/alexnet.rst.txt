===========================
Detecting Oranges - alexnet
===========================

-   1-2. 이미지에서 오렌지 검출 - alexnet.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/alexnet1.webp


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    # Check the original image
    run_command_before = 'bash ~/ai_example/show.sh orange before'
    subprocess.call((run_command_before.split('\n')), shell=True)


-   Check the original image

.. thumbnail:: /_images/ai_training/googlenet2.png


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_before = 'bash ~/ai_example/kill.sh display'
    subprocess.call((kill_command_before.split('\n')), shell=True)


-   Terminating the process

.. code-block:: python

    # Detect objects
    detect_command_orange = 'bash ~/ai_example/detect.sh orange_alexnet'
    subprocess.call((detect_command_orange.split('\n')), shell=True)

-   Detecting objects


.. code-block:: python

    # Check the detected image
    run_command_after = 'bash ~/ai_example/show.sh orange after alexnet'
    subprocess.call((run_command_after.split('\n')), shell=True)

-   Check the detected image

.. thumbnail:: /_images/ai_training/alexnet2.png

-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_after = 'bash ~/ai_example/kill.sh display'
    subprocess.call((kill_command_after.split('\n')), shell=True)

-   Terminating the process