.. _containerization:

.. containerization
.. ============

The following  document briefly details how user/developers  of DEST can  package it into containers


Docker
=============
The platform of Docker is used as a service products that provides some degree of flexibility for developers to build, share, and run modern applicationsuse in packages called containers. In the following we will provide an example on how to configure and build DEST on a container, and later being able to run it inside Docker container.

Installing Docker
==================
.. image:: ../../images/doc.png
   :alt: Docker
   :target: https://www.docker.com/
   :class: with-shadow
   :scale: 50

First, you should download Docker (links to the various Docker versions on the Docker website: https://www.docker.com and https://docs.docker.com)

Once you have downloaded and installed it on your system, you can follow the following instructions. 

Enter your work directory and clone the DEST code into a folder, e.g. DEST-master

    .. code-block:: console
		
		cd /data/yours
                git clone https://gitlab.DEST_master 
    
    
In the root folder of DEST you can find a file with the name Dockerfile which will be used by docker build command to build Docker images from a Dockerfile and a “context”.

open a terminal at the root folder of DEST and run the following to remove all unused containers, networks, images
     .. code-block:: console

           docker image prune -a 
	   
as shown in the following figure

 .. image:: ../../images/d1.png
   :alt: DO1 
   :align: center
   :class: with-shadow
   :scale: 70	   

then check it with the following command 

     .. code-block:: console
           
	   docker image ls
	   
 .. image:: ../../images/d2.png
   :alt: DO2 
   :align: center
   :class: with-shadow
   :scale: 70		   
	   
          
now you can run the build command

     .. code-block:: console
           
	   docker build .

 .. image:: ../../images/d3.png
   :alt: DO3 
   :align: center
   :class: with-shadow
   :scale: 70	
   
.. Note:: For more detailed approach visit https://docs.docker.com/engine/reference/commandline/build/.


after build was processed successfully you will see the following information about the docker image

 .. image:: ../../images/d4.png
   :alt: DO4 
   :align: center
   :class: with-shadow
   :scale: 70

next you can run for example the following to tag the image

     .. code-block:: console
           
	   docker tag a1b004da18e5  dest/dest_oxford_32_run:latest
	   
	   
 .. image:: ../../images/d5.png
   :alt: DO5 
   :align: center
   :class: with-shadow
   :scale: 70

finally, for testing the executable file you can run the following

  .. code-block:: console

            docker run --rm dest/dest_oxford_32_run:latest  ./BIN/DEST_analyser_Debug  -filename  TESTS/B_013/B_013.dat

 .. image:: ../../images/d6.png
   :alt: DO6 
   :align: center
   :class: with-shadow
   :scale: 70

In order to copy the results from the container to the host, first create a folder on host machine (e.g. results-container-to-host) you can use the following command (with updated path!)

    .. code-block:: console
    
         docker run -it dest/dest_oxford_32_run:latest  /bin/bash
	 
         scp  TESTS/B_013/*   kevinb@kevin-XPS:/home/kevinb/Desktop/results-container-to-host
   
   
 .. image:: ../../images/d7.png
   :alt: DO7 
   :align: center
   :class: with-shadow
   :scale: 70
   
  .. image:: ../../images/d8.png
   :alt: DO8 
   :align: center
   :class: with-shadow
   :scale: 70  

congratulations, you have now built and run DEST using Docker.

Singularity 
==============
Singularity is a free computer program. Singularity brings containers and reproducibility to scientific computing and the high-performance computing, Similar to the platform of Docker, it is used as a service products that provides some degree of flexibility for developers to build, share, and run modern applicationsuse in packages called containers. In the following we will provide an example on how to configure,build and run DEST on a Singularity container. 

Installing Singularity
==================

.. image:: ../../images/sing1.png
   :alt: Singu
   :target: https://docs.sylabs.io/guides/3.5/user-guide/introduction.html
   :class: with-shadow
   :scale: 50

First, you should install Singularity on your system (links to a online guidance for running Singularity on a computer, Singularity website: https://docs.sylabs.io/guides/3.5/user-guide/quick_start.html)



Once you have installed it on your system, you can follow the following instructions. 
After building  successfully Docker image you can use it (or use the following image) to build Singularity image

     .. code-block:: console
           
	   singularity build singularity_dest.sif docker://kbronik/dest_oxford_32_run:latest

  .. image:: ../../images/sing2.png
   :alt: Singu2
   :align: center
   :class: with-shadow
   :scale: 70 


after build was processed successfully you will see the following information about the singularity image

 .. image:: ../../images/sing3.png
   :alt: Singu3 
   :align: center
   :class: with-shadow
   :scale: 70
   
finally, for testing the executable file you can run the following (where /home/kevinb/Desktop/testing/B_013.dat is an existing folder on your local system or cluster/HPC system) 

  .. code-block:: console

            singularity exec  singularity_dest.sif  /home/executiveuser/BIN/DEST_analyser_Debug  -filename  /home/kevinb/Desktop/testing/B_013.dat

 .. image:: ../../images/sing4.png
   :alt: Singu4 
   :align: center
   :class: with-shadow
   :scale: 70   
   

congratulations, you have now built and run DEST using Docker and Singularity.   
