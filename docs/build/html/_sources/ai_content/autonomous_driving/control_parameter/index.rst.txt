=================
Control Parameter
=================


1. Modification of parameters by direct navigation into the folder
------------------------------------------------------------------

.. code-block:: bash

    $ cd ~/zeta_edu_package/zeta_navigataion/param

.. code-block:: bash 

    $ gedit @@(parameter name you wish to edit).yaml

Then enter the desired values and save. After completion, the navigation will run with the corresponding parameters.

2. Entering parameter values in real time on the GUI
----------------------------------------------------

First, run the navigation, then run a new terminal and enter the command below.

.. code-block:: bash

    $ rosrun rqt_reconfigure rqt_reconfigure

.. image:: /_images/autonomous_driving/gui.png


When the corresponding screen is executed, judge the performance of the navigation in real time by adjusting the values suitable for each parameter.

**Precautions) If you adjust many parameter values at once, navigation may stop. Therefore, change the value little by little, paying attention to the phenomena appearing on RVIZ.**

.. toctree::
    :hidden:

    self
    inflation_layer
    cost_scaling