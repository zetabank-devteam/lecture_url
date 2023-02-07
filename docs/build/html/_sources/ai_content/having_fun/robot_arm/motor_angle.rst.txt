======================
Read Servo Motor Angle
======================


-   05_02_read_servo.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/rob_arm1.png

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

    # Read the angles of all servos.
    def main():

        while True:
            for i in range(6):
                aa = Arm.Arm_serial_servo_read(i+1)
                print(aa)
                time.sleep(.01)
            time.sleep(.5)
            print(" END OF LINE! ")

        
    try :
        main()
    except KeyboardInterrupt:
        print(" Program closed! ")
        pass


-   Arm_serial_servo_read (motor number)
-   Read all servo motor angles using while statement

.. code-block:: python

    # After individually controlling the movement of the servos, the angle is read.
    id = 3
    angle = 41

    Arm.Arm_serial_servo_write(id, angle, 500)
    time.sleep(1)

    aa = Arm.Arm_serial_servo_read(id)
    print(aa)

    time.sleep(.5)


-   Arm_serial_servo_write (motor number, angle, time)
-   Read angle after controlling servo motor No. 3

.. code-block:: python

    del Arm  # Remove robot arm object


-   Remove object (Robot arm)