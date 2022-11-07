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
   :scale: 30

First, you should download Docker (links to the various Docker versions on the Docker website: https://www.docker.com and https://docs.docker.com)

Once you have downloaded and installed it on your system, you can follow the following instructions. 

For example:

    .. code-block:: console
		
		user@login*:~> bash Miniconda3-latest-Linux-x86_64.sh
    
    

Singularity 
==============
Installing Singularity
==================
.. image:: ../../images/ac.png
   :alt: Miniconda
   :target: https://docs.conda.io/en/latest/miniconda.html
   :class: with-shadow
   :scale: 30

First, you should download Miniconda (links to the various miniconda versions on the Miniconda website: https://docs.conda.io/en/latest/miniconda.html)

.. Note:: If you wish to use Python on the Archer2's compute nodes then you must install Miniconda in your /work directories as these are the only ones visible on the compute nodes.


Once you have downloaded the installer, you can run it. 
For example:

    .. code-block:: console
		
		user@login*:~> bash Miniconda3-latest-Linux-x86_64.sh
