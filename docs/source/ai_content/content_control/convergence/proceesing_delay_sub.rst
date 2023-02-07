===========================
Processing Delay Subscriber
===========================


-   1_2_처리지연_receiver.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/conv2.png


.. code-block:: python

    import rospy
    from std_msgs.msg import Int32

-   Import rospy modules
-   Import Int32 from std_msgs.msg module



.. code-block:: python

    rospy.init_node('Receiver')

-   Create Receiver Node


.. code-block:: python

    pre_num = 0
    cur_num = 0

-   Set variable pre_num to 0
-   Set variable cur_num to 0

.. code-block:: python

    def callback(msg):
        global pre_num
        global cur_num
        
        print("Callback is being processed")
        cur_num = msg.data
        rospy.sleep(3)
        
        if (cur_num - pre_num) != 1:
            print_str = "Data: {0:>6}    Missing: {1:6} ~ {2:>6} (  cnt: {3}  )\n"\
            .format(msg.data,pre_num +1, cur_num -1, cur_num - pre_num -1)
        else:
            print_str = "Data: " + str(msgs.data) + "\n"
        
        print(print_str)
        pre_num = cur_num


-   Create callback(msg) function
-   Declare pre_num and cur_num as global variables
-   Designate cur_num as message data
-   3 second time delay
-   cur_num - if pre_num is not 1,

    -   Output in order of message data, pre_num + 1, cur_num -1, cur_num - pre_num -1
    -   Data: (current data) Missing: (minimum value of missing data ~ maximum value of missing data) (cnt: (number of missing data))

-   Other cases

    -   Message data output

-   Specify pre_num as cur_num

.. code-block:: python

    sub = rospy.Subscriber('increase_num', Int32, callback, queue_size=1)
    rospy.spin()

-   Create increase_num Topic Subscriber