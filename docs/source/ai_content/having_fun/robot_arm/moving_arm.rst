====================
Moving the Robot Arm
====================

-   05_01_left_right.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/arm1.webp

.. code-block:: python

    #!/usr/bin/env python3
    #coding=utf-8
    import time
    from Arm_Lib import Arm_Device

    # Register robot arm as an object
    Arm = Arm_Device()
    time.sleep(.1)

-   Load Arm_Lib module and register the robot arm as an object


.. code-block:: python

    # Repeat swinging the robot arm up and down
    # Arm range = 0 ~ 180
    def main():
        # Make all servos in the middle.
        Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 500)
        time.sleep(1)


        while True:
            # Move servos 3 and 4 up and down
            Arm.Arm_serial_servo_write(3, 0, 1000)
            time.sleep(.001)
            Arm.Arm_serial_servo_write(4, 180, 1000)
            time.sleep(1)
            
            # Move the 1st and 5th servos left and right.
            Arm.Arm_serial_servo_write(1, 180, 500)
            time.sleep(.001)
            Arm.Arm_serial_servo_write(5, 180, 500)
            time.sleep(0.51)
            Arm.Arm_serial_servo_write(1, 0, 1000)
            time.sleep(.001)
            Arm.Arm_serial_servo_write(5, 0, 500)
            time.sleep(1.1)
            
            # Move servo to initial position.
            Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 1000)
            time.sleep(1.5)


    try :
        main()
    except KeyboardInterrupt:
        print(" Program closed! ")
        pass


-   Arm_serial_servo_write6 (motor 1, motor 2, motor 3, motor 4, motor 5, motor 6, time)
-   Arm_serial_servo_write (motor number, angle, time)
-   Adjust the No. 3 servo motor to 0˚ and the No. 4 servo motor to 180˚
-   Adjust the number 1 and 5 servo motors from 180˚ -> 0˚

.. code-block:: python

    del Arm  # Remove robot arm object


-   Remove object (Robot arm)