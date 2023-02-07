==================
Robot Arm teaching
==================

-   05_05_study_mode.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/teaching1.png

.. code-block:: python

    #!/usr/bin/env python3
    #coding=utf-8
    import time
    from Arm_Lib import Arm_Device

    Arm = Arm_Device()
    time.sleep(.1)

-   Load Arm_Lib module and register the robot arm as an object


.. code-block:: python

    # If you use the learning mode, the torque of the robot arm is released and it can move.
    # In learning mode, you can manually control the robot arm.
    Arm.Arm_Button_Mode(1)
    

.. code-block:: python

    # This is where you register your learning.
    # Whenever the arm is moved and executed, the motion is registered. (20 motions)
    Arm.Arm_Action_Study()


.. code-block:: python

    # Exit learning mode.
    Arm.Arm_Button_Mode(0)


.. code-block:: python

    # Indicates the number of stored lessons.
    num = Arm.Arm_Read_Action_Num()
    print(num)


.. code-block:: python

    # Execute the learned motion once.
    Arm.Arm_Action_Mode(1)


.. code-block:: python

    # Repeat the learned motion.
    Arm.Arm_Action_Mode(2)

.. code-block:: python

    # Stop motion (learned motion).
    Arm.Arm_Action_Mode(0)

.. code-block:: python 

    # Initialize the learned motion.
    Arm.Arm_Clear_Action()

-   Robot arm teaching and learned motion execution

.. code-block:: python

    del Arm  # Release DOFBOT object


-   Remove object (Robot arm)