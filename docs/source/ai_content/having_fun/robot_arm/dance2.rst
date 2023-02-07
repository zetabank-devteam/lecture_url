===============
Robot Dance - 1
===============


-   05_09_music_dance.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/arm_dance2.png

-   Robot arm dance example with exciting music - 2

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
    music = mixer.Sound('music.ogg')
    bomb = mixer.Sound('bomb.ogg')
    music.set_volume(0.02)
    bomb.set_volume(0.1)

-   Initialize the sound file

.. code-block:: python

    # Initialization
    Arm.Arm_serial_servo_write6(0, 90, 0, 180, 90, 90, 2000)

-   Initialize the robot arm location

.. code-block:: python

    while(1):
        music.play()
        # 모터 범위 0~180
        Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 2000)
        time.sleep(2.1)
        Arm.Arm_serial_servo_write6(180, 90, 0, 180, 90, 90, 2000)
        time.sleep(2.1)
        Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 2000)
        time.sleep(2.1)
        Arm.Arm_serial_servo_write6(0, 90, 0, 180, 90, 90, 2000)
        time.sleep(2.1)
        Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 2000)
        time.sleep(2.1)
        Arm.Arm_serial_servo_write6(180, 90, 0, 180, 90, 90, 2000)
        time.sleep(2.1)
        Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 1600)
        time.sleep(1.61)
        Arm.Arm_serial_servo_write6(90, 90, 0, 90, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(0, 90, 0, 180, 0, 180, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(180, 90, 0, 180, 180, 180, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(0, 90, 0, 180, 0, 180, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(180, 90, 0, 180, 180, 180, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(180, 90, 0, 180, 180, 180, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(0, 90, 0, 180, 0, 180, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 180, 90, 90, 600)
        time.sleep(0.82)
        Arm.Arm_serial_servo_write6(90, 90, 0, 90, 90, 90, 1500)
        time.sleep(1.5)
        Arm.Arm_serial_servo_write6(90, 90, 0, 90, 90, 180, 500)
        time.sleep(1.5)
        music.stop()
        bomb.play()
        break

-   Play the music and the dance at the same time

.. code-block:: python

    my_sound.stop()

-   Terminate sound

