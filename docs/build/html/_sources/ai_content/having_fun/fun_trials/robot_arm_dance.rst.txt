=============
Dancing Robot
=============


Lets dance with our robots
--------------------------

.. thumbnail:: /_images/having_fun/dancegit.png

-   1. 로봇팔.댄스.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/having_fun/robot_arm_dance.webp

-   Randomly moving robot arm dance

.. code-block:: python

    !pm2 start 13 15 > /dev/null
    !pm2 stop 14 > /dev/null
    !pm2 status


.. code-block:: python

    import rospy
    import time
    import random
    from pygame import mixer
    from std_msgs.msg import Float32MultiArray

.. code-block:: python

    def dance():
        cnt = 0
        
        mixer.init(48000, 16, 2, 2048)
        music = mixer.Sound('next_level.ogg')
        music.set_volume(0.02)
        music.play()
        time.sleep(7)
        
        dofbot_pub = rospy.Publisher('point_gripper', Float32MultiArray, queue_size=10)
        rospy.init_node('dundundance', anonymous=True)
        
        while not rospy.is_shutdown():
            msg = Float32MultiArray()
            msg.data.append(random.randrange(-5, 5, 1))
            msg.data.append(random.randrange(-10, 10, 1))
            msg.data.append(random.randrange(25, 40, 1))
            msg.data.append(random.randrange(50, 180, 1))
            #rospy.loginfo(msg)
            dofbot_pub.publish(msg)
            rospy.sleep(2.0)
            cnt += 1
            print(cnt)
            
            if cnt == 75:
                break
                
        music.stop()
        rospy.signal_shutdown("killed")


.. code-block:: python

    try:
        dance()
    except rospy.ROSInterruptException:
        pass

