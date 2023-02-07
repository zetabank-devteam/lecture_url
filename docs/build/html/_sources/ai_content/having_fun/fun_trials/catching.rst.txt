==============
Catching Robot
==============


Let play catch with our robots
------------------------------

.. thumbnail:: /_images/having_fun/catch_monster_streaming.png





-   2. 뽑기.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/drawing.webp

-   3 minute time limit
-   Use the joystick to pick up objects

.. code-block:: 

    !pm2 start 11 13 14 > /dev/null
    !pm2 stop 15 > /dev/null
    !pm2 status


.. code-block:: python

    import rospy
    import random
    import time
    import subprocess
    from std_msgs.msg import Int32MultiArray
    from IPython.display import clear_output

.. code-block:: python

    def timer():
        sec = 0
        min = 0
        sound_pub = rospy.Publisher('robot_sound', Int32MultiArray, queue_size=1)
        rospy.init_node('gotcha', anonymous=True)
        packet = Int32MultiArray()
        
        while not rospy.is_shutdown():
            clear_output()
            print("Timer : " + str(min) + " minutes " + str(sec) + " seconds passed")
            time.sleep(1)
            sec += 1
            
            if min == 0 and sec == 1:
                packet.data = [1, 14, 1]
                sound_pub.publish(packet)
            
            if sec == 60:
                sec = 0
                min += 1
                
            if min <= 2 and sec > 10:
                if sec % 15 == 0:
                    packet.data = [1, random.randrange(1, 11, 1), 1]
                    sound_pub.publish(packet)
                    
            if min == 2 and sec == 0:
                packet.data = [1, 0, 1]
                sound_pub.publish(packet)
                
            if min == 3 and sec == 0:
                packet.data = [1, 13, 1]
                sound_pub.publish(packet)
                command = "pm2 stop 11 && rostopic pub -1 /cmd_vel geometry_msgs/Twist '{linear: {x: 0.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}'"
                subprocess.call((command.split('\n')), shell=True)
                break
                
        rospy.signal_shutdown("killed")


.. code-block:: python

    try:
        timer()
    except rospy.ROSInterruptException:
        pass

