===================
Time Slot Publisher
===================

-   2_1_타임슬롯_sender.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/conv3.png


.. code-block:: python

    import rospy
    from std_msgs.msg import Int32
    import time

-   Import rospy modules
-   Import Int32 from std_msgs.msg module
-   Import time module


.. code-block:: python

    rospy.init_node( 'Sender', anonymous=False)
    pub = rospy.Publisher('my_topic', Int32, queue_size=0)

-   Create Sender Node
-   my_topic Topic Publish


.. code-block:: python

    def do_job(num):
        for i in range(num):
            i += 1
            pub.publish(i)

-   Create do_job(num) function
-   Adds days to i until i equals num, then publishes Message i

.. code-block:: python

    print("")
    r = input('Rate: ') #How big is the size of one time slot? = (1/r) seconds
    num = input('Num: ') #How many to send = (1/r) Number of data to send per second
    print("")

    rate = rospy.Rate(r)
    elapsed_total = 0

    for _ in range(r):
        start_send = rospy.get_time()
        do_job(num)
        end_send = rospy.get_time()
        elapsed_sending = end_send - start_send

        start_sleep = rospy.get_time()
        rate.sleep()
        end_sleep = rospy.get_time()
        elapsed_sleep = end_sleep - start_sleep
        
        print(" Send: %.5f sec" % elapsed_sending)
        print("Sleep: %.5f sec" % elapsed_sleep)
        print("Total: %.5f sec\n" % (elapsed_sending + elapsed_sleep))
        
        elapsed_total += (elapsed_sending + elapsed_sleep)

    print("\n------------- [Report]--------------")
    print("It took %.5f seconds to send data" % elapsed_total)
    print("-------------------------------------")


-   Specify r and num as user input
-   Set rate to r
-   Set the elapsed_total variable to 0
-   Execute the for statement r times

    -   Set the start_send variable to the current Timestamp
    -   Execute the do_job(num) function
    -   Set the start_send variable to the current Timestamp
    -   Set the elapsed_sending variable to end_send - start_send
    -   Set the start_sleep variable to the current Timestamp
    -   Time delay for rate
    -   Set the end_sleep variable to the current Timestamp
    -   Set the elapsed_sleep variable to end_sleep - start_sleep
    -   Output elapsed_sending, elapsed_sleep, (elapsed_sending + elapsed_sleep)
    -   Add (elapsed_sending + elapsed_sleep) to elapsed_total
-   elapsed_total output

    -   Total time to send rate, sleep, and data after sending data as much as the number of num in 1/r second
    -   As the number of data to be sent for 1/r second increases, sleep decreases.
