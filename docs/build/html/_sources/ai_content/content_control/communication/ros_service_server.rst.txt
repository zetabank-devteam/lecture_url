==================
ROS Service Server
==================


-   02_01_ros_service_server.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/comm10.webp

.. thumbnail:: /_images/content_control/comm11.webp

.. code-block:: python

    from __future__ import print_function
    from rospy_tutorials.srv import AddTwoInts,AddTwoIntsResponse
    import rospy
    
-   Import print_function from `__future__` module for Python3 compatibility
-   Import AddTwoInts, AddTwoIntsResponse from rospy_tutorials.srv module
-   Import rospy modules

.. code-block:: python

    def handle_add_two_ints(req):
        print("Returning [%s + %s = %s]"%(req.a, req.b, (req.a + req.b)))
        return AddTwoIntsResponse(req.a + req.b)

-   Create handle_add_two_ints() function
-   Output req.a, req.b, req.a + req.b
-   Return instances of req.a + req.b in AddTwoIntsResponse

.. code-block:: python

    def add_two_ints_server():
        rospy.init_node('add_two_ints_server')
        s = rospy.Service('add_two_ints', AddTwoInts, handle_add_two_ints)
        print("Ready to add two ints.")
        rospy.spin()

-   Create `add_two_ints_server()` function
-   Create add_two_ints_server Node
-   Create add_two_ints Service

.. code-block:: python

    add_two_ints_server()

-   Create add_two_ints_server() function
