===============
Robot Dance - 1
===============


-   05_09_carri_dance.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/arm_dance1.png

-   Robot arm dance example with exciting music - 1

.. code-block:: python

    from pygame import mixer
    import time
    from Arm_Lib import Arm_Device

    # register the robot arm as an object
    Arm = Arm_Device()
    time.sleep(.1)

-   Load Arm_Lib module and register the robot arm as an object


.. code-block:: python

    # Register ogg file 
    mixer.init(48000, 16, 2, 2048)
    my_sound = mixer.Sound('music.ogg')
    my_sound.set_volume(0.01)

-   Initialize the sound file

.. code-block:: python

    # Initialization
    Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 1000)

-   Initialize the robot arm location

.. code-block:: python

    while(1):
        my_sound.play()
        # 1st move
        Arm.Arm_serial_servo_write(3, 0, 1500)
        time.sleep(.001)
        Arm.Arm_serial_servo_write(4, 180, 1500)
        time.sleep(.001)
        Arm.Arm_serial_servo_write(1, 0, 1500)
        time.sleep(5.5)
        # 2nd move
        Arm.Arm_serial_servo_write(1, 90, 500)
        time.sleep(1.5)
        # 3rd move
        Arm.Arm_serial_servo_write(1, 180, 500)
        time.sleep(1.5)
        # 4th move
        Arm.Arm_serial_servo_write(3, 90, 500)
        time.sleep(.001)
        Arm.Arm_serial_servo_write(4, 90, 500)
        time.sleep(1.5)
        # 5th move
        Arm.Arm_serial_servo_write(3, 0, 500)
        time.sleep(.001)
        Arm.Arm_serial_servo_write(4, 180, 500)
        time.sleep(1.5)
        # 6th move
        Arm.Arm_serial_servo_write(1, 90, 1000)
        time.sleep(1.5)
        # 7th move
        Arm.Arm_serial_servo_write(1, 0, 1000)
        time.sleep(1.5)
        my_sound.stop()
        break

-   Play the music and the dance at the same time

.. code-block:: python

    my_sound.stop()

-   Terminate sound

.. code-block:: python

    Arm.Arm_serial_servo_write(3, 0, 500)
    time.sleep(.001)
    Arm.Arm_serial_servo_write(4, 180, 500)

.. code-block:: python

    Arm.Arm_serial_servo_write(1, 0, 1000)

.. code-block:: python

    Arm.Arm_serial_servo_write6_array(joints_4, 1500)

.. code-block:: python

    Arm.Arm_serial_servo_write(3, 90, 500)
    time.sleep(.001)
    Arm.Arm_serial_servo_write(4, 90, 500)


.. code-block:: python

    Arm.Arm_serial_servo_write(3, 0, 500)
    time.sleep(.001)
    Arm.Arm_serial_servo_write(4, 180, 500)

-   Movement complete