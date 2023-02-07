=============================
Write '10 lines' example code
=============================


-   7. 10줄 예제 작성해보기.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/ai_training/training1.png

-   Used Language: Python
-   Real-time object detection code using Raspberry Pi Camera

.. thumbnail:: /_images/ai_training/training2.png


.. code-block:: python

    import jetson_inference
    import jetson_utils

    net = jetson_inference.detectNet("ssd-mobilenet-v2", threshold=0.5)
    camera = jetson_utils.videoSource("csi://0") # Raspberry Pi Camera
    display = jetson_utils.videoOutput("display://0") # Jetson Nano Display

    while display.IsStreaming():
        img = camera.Capture()
        detections = net.Detect(img)
        display.Render(img)
        display.SetStatus("Object Detection | Network {:.0f} FPS".format(net.GetNetworkFPS()))

-   7. Write and modify code in example_tenline.py file


.. code-block:: python

    import subprocess


-   Import the subprocess module


.. code-block:: python

    # Try the 10 line example
    run_example = 'bash ~/ai_example/example_tenline.sh'
    subprocess.call((run_example.split('\n')), shell=True)

-   Try the 10 line example

.. thumbnail:: /_images/ai_training/training3.png

-   Executed on Jetson Nano

.. code-block:: python

    # terminating the process
    kill_example = 'bash ~/ai_example/kill.sh camera'
    subprocess.call((kill_example.split('\n')), shell=True)

-   Terminating the Process