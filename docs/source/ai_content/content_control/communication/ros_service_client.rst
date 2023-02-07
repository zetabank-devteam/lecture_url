==================
ROS Service Client
==================


-   02_02_ros_service_client.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/comm12.png

.. thumbnail:: /_images/content_control/comm13.png

.. code-block:: python

    from __future__ import print_function
    import sys
    import rospy
    from rospy_tutorials.srv import *
    
-   Import print_function from __future__ module for Python3 compatibility
-   Import sys module
-   Import rospy_tutorials.srv module
-   Import rospy modules



.. code-block:: python

    def add_two_ints_client(x, y):
        rospy.wait_for_service('add_two_ints')
        try:
            add_two_ints = rospy.ServiceProxy('add_two_ints', AddTwoInts)
            resp1 = add_two_ints(x, y)
            return resp1.sum
        except rospy.ServiceException as e:
            print("Service call failed: %s"%e)

-   Create add_two_ints_client()  function
-   Create add_two_ints_client() 
-   Get add_two_ints Service result
-   exception handling

.. code-block:: python

    def usage():
        return "%s [x y]"%sys.argv[0]

.. code-block:: python

    input_num = input("숫자 두 개를 입력하세요(ex: a,b) : ")
    x = int(input_num[0])
    y = int(input_num[1])
    print("Requesting %s+%s"%(x, y))
    print("%s + %s = %s"%(x, y, add_two_ints_client(x, y)))

-   Get user input x, y
-   Service result output
