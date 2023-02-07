======================
ROS 2 (Raspberry)
======================

.. image:: /_images/ai_autonomous_robot/ros_jets.webp  

* ROS 2 Features

  1. Multi-platform support (Linux, macOS, Windows)

     - Can be installed on various OS such as Windows, macOS, Linux
  
  2. Real Time Control (RTPS, Real Time Publish Subscribe)
  
     - Selectable best-effort and reliable publish subscribe communication over standard IP networks

  3. Supports various technologies such as Zeroconf, Protocol Buffers, ZeroMQ, and WebSockets
  4. Using DDS middleware using Dynamic Discovery instead of roscore
     - No distinction between ROS Master and Client

  5. Communication using XMLRPC, TCPROS protocol
  6. Improved build tool using ament tool instead of catkin tool

     - CMake-based catkin cannot manage python packages, only available in single workspace

  7. Improvement of security vulnerabilities using a separate ID instead of ROS Master's IP and PORT

     - Improved risk of system attack when IP and PORT are exposed