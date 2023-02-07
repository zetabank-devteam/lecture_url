Object Detection
==================

Object Detection, in the context of Computer Vision is a computer's ability
to recognize and locate an object through an image, a video or a live camera. 


For Object Detection task, we use the pre-built detectnet program. The program takes
an input (an image, a video or a live camera) and performs the inference using the
pretrained networks, then outputs the coordinates of the recognized input. We overlay 
a box with recognized name using the coordinates on top of our original input.  


There are total of 10 networks that are designed and trained to detect and locate different
objects. 

.. list-table:: 
   :header-rows: 1

   * - Network
     - CLI argument
     - Classes
   * - SSD-Mobilenet-v1
     - ssd-mobilenet-v1
     - 91 ()
   * - SSD-Mobilenet-v2
     - ssd-mobilenet-v2
     - 91 ()
   * - SSD-Inception-v2
     - ssd-inception-v2
     - 91 ()
   * - DetectNet-COCO-Dog
     - coco-dog
     - dogs
   * - DetectNet-COCO-Bottle
     - coco-bottle
     - bottles
   * - DetectNet-COCO-Chair
     - coco-chair
     - chairs
   * - DetectNet-COCO-Airplane
     - coco-airplane
     - airplanes
   * - ped-100
     - pednet
     - pedestrians
   * - multiped-500
     - multiped
     - pedestrians, luggage
   * - facenet-120
     - facenet
     - faces


Launching the Program
----------------------

The detectnet program is a python based program. The program may be ran directly on the Command Line Interface
or through our pre-built script ran on the Jupyter Notebook environment. 


These are the different parameters that can the adjusted to the users need. 
**(Note)** The input and output information must be given. 

- The network name that will be used for the inference
- The input source (file path if it is an image(s) or a video(s))
- The output method (file path if it is an image(s) or a video(s))


.. code-block:: bash

    ./detectnet.py --networks=<network name> <input source> <output method>


Examples through Jupyter Notebook
----------------------------------

The program launching process along with parameter settings are all simplified and set up on the Jupyter Notebook Environment. 

(The Jetson Board used for these examples are => Jetson Nano)

.. toctree:: 

  det_car
  det_ped
  det_dog
  det_obj
  det_face
  det_dog_cam
