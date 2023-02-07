TAO CLI Pre-Requisite Installation Guide
=============================================

**(Note!!!)** There are 2 Methods to get TAO running on a system 
(CLI launch and Container launch). This guide only covers the CLI 
Launch Methods. 

.. raw:: html

   <hr>


- **Installing Docker:**
    
    Docker is an open source platform for building, deploying and managing container as applications.
    
    Within the terminal install the most recent docker:

    .. code-block:: bash

        curl https://get.docker.com | sh \
        > && sudo systemctl --now enable docker

- **Installing NVIDIA container:**
    
    .. code-block:: bash
        
        distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
        > && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - \
        > && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt sources.list.d/nvidia-docker.list
    
    
    .. code-block:: bash
    
        sudo apt-get update
    
    
    .. code-block:: bash
        
        sudo apt-get install -y nvidia-docker2
    
    
    .. code-block:: bash

        sudo systemctl restart docker
    
    
    **IMPORTANT!!!** Make sure the system cuda version is the same as the one being installed on the docker cuda
    
    **IMPORTANT!!!** Install the latest version of cuda ([https://hub.docker.com/r/nvidia/cuda](https://hub.docker.com/r/nvidia/cuda))
    
    .. code-block:: bash
    
        sudo docker run --rm --gpus all nvidia/cuda:12.0.0-base-ubuntu20.04 nvidia-smi
    
    
    - **Test all the installation with**
    
    .. code-block:: bash

        docker login nvcr.io
    
    
    - NGC Account
        - For this step, one must log into the NGC NVIDIA account and gain their individual api token. After the token is inputted into the (`<http://nvcr.io>`_) (next step)
    - Python Virtual Environment (conda installation recommended)
        - Create a virtual environment with python ≥ 3.6.9
            - for conda initialization bash path might need to be established
            
            .. code-block:: bash

                source ~/miniconda3/etc/profile.d/conda.sh
            

    **(Note!!!) The NVIDIA Provides getting started pack with necessary libraries**

- Installing pre-requisite files
    
    .. code-block:: bash
        
        wget --content-disposition https://api.ngc.nvidia.com/v2/resources/nvidia/tao/tao-getting-started/versions/4.0.0/zip -O getting_started_v4.0.0.zip
        unzip -u getting_started_v4.0.0.zip  -d ./getting_started_v4.0.0 && rm -rf getting_started_v4.0.0.zip && cd ./getting_started_v4.0.0
    
    
- **Install TAO launcher with the getting started pack**
    
    .. code-block:: bash
    
        bash setup/quickstart_launcher.sh --install
    
    
    - Check for TAO version. If There exists errors or dependency problems when ``tao info`` line is run, check the cuda version of the host file and cuda version of docker.
    - When running the TAO launcher, some dependency issue might appear.

- Update the launcher
    
    .. code-block:: bash
        
        bash setup/quickstart_launcher.sh --upgrade
    
    
    - Make sure that there are no warnings, (especially GPU dependency warning!!!)
        
        Example output (``tao —help``):

        .. code-block:: bash 

            usage: tao [-h]
                    {list,stop,info,action_recognition,augment,bpnet,classification_tf1,classification_tf2,converter,deformable_detr,detectnet_v2,dssd,efficientdet_tf1,efficientdet_tf2,emotionnet,faster_rcnn,fpenet,gazenet,gesturenet,heartratenet,intent_slot_classification,lprnet,mask_rcnn,multitask_classification,n_gram,pointpillars,pose_classification,punctuation_and_capitalization,question_answering,re_identification,retinanet,segformer,spectro_gen,speech_to_text,speech_to_text_citrinet,speech_to_text_conformer,ssd,text_classification,token_classification,unet,vocoder,yolo_v3,yolo_v4,yolo_v4_tiny}
                    ...

            Launcher for TAO Toolkit.

            optional arguments:
            -h, --help            show this help message and exit

            tasks:
            {list,stop,info,action_recognition,augment,bpnet,classification_tf1,classification_tf2,converter,deformable_detr,detectnet_v2,dssd,efficientdet_tf1,efficientdet_tf2,emotionnet,faster_rcnn,fpenet,gazenet,gesturenet,heartratenet,intent_slot_classification,lprnet,mask_rcnn,multitask_classification,n_gram,pointpillars,pose_classification,punctuation_and_capitalization,question_answering,re_identification,retinanet,segformer,spectro_gen,speech_to_text,speech_to_text_citrinet,speech_to_text_conformer,ssd,text_classification,token_classification,unet,vocoder,yolo_v3,yolo_v4,yolo_v4_tiny}