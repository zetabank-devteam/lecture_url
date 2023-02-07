========================
Controlling Servo Motors
========================


-   05_03_ctrl_all.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/motor_cont1.webp

.. code-block:: python

    #!/usr/bin/env python3
    #coding=utf-8
    import time
    from Arm_Lib import Arm_Device

    # register the robot arm as an object
    Arm = Arm_Device()
    time.sleep(.1)

-   Load Arm_Lib module and register the robot arm as an object


.. code-block:: python

    # It gradually changes the angle while controlling 6 servos at the same time.
    def ctrl_all_servo(angle, s_time = 500):
        Arm.Arm_serial_servo_write6(angle, 180-angle, angle, angle, angle, angle, s_time)
        time.sleep(s_time/1000)


    def main():
        dir_state = 1
        angle = 90

        Arm.Arm_serial_servo_write6(90, 90, 90, 90, 90, 90, 500)
        time.sleep(1)

        
        while True:
            if dir_state == 1:
                angle += 1
                if angle >= 180:
                    dir_state = 0
            else:
                angle -= 1
                if angle <= 0:
                    dir_state = 1
            
            ctrl_all_servo(angle, 10)
            time.sleep(10/1000)
    #         print(angle)

        
    try :
        main()
    except KeyboardInterrupt:
        print(" Program closed! ")
        pass


-   Arm_serial_servo_write (motor number, angle, time)
-   Increase and decrease all servo motor angles by 1˚ using a while statement



.. code-block:: python

    del Arm  # Remove robot arm object


-   Remove object (Robot arm)