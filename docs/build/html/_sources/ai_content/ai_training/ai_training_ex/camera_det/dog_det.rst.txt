==============
Detecting Dogs
==============


-   3-3. 카메라로 강아지 객체 검출.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/dog_det1.webp


.. code-block:: python

    import subprocess

-   Import the subprocess module


.. code-block:: python

    # Detecting dogs with Raspberry Pi Camera
    detect_command_dog = 'bash ~/ai_example/detect.sh cam_dog'
    subprocess.call((detect_command_dog.split('\n')), shell=True)

-   Detecting dogs with Raspberry Pi Camera

.. thumbnail:: /_images/ai_training/dog_det2.webp


-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_command_face = 'bash ~/ai_example/kill.sh camera'
    subprocess.call((kill_command_dog.split('\n')), shell=True)


-   Terminating the process
