.. _execution:



Integrated Development Environment (IDE)
=======================
This document briefly details how user/developers can  use C/C++ integrated development environments (C/C++ IDEs) that provide a comprehensive set of tools for DEST development, in the C and/or C++ programming languages

How to build and run on Visual Studio 
=======================

Currently the only IDE that can generate all three executables (DEST_analyser, DEST_optimiser and DEST_conveyor) for Windows. 

The "make" (as an older version of "cmake") approach to compiling and linking the code on all platforms should also work, but needs updating to ensure that is works (rather than just on Linux) on Windows and macOS. 	




How to build and run on Visual Studio Code 
=====================

Visual Studio Code download 


Visual Studio Code Docs Documentation for Visual Studio Code, including Getting Started videos Visual Studio Code Introductory Videos 


Open DEST repository (http://isml-grs.eng.ox.ac.uk:8000) 



How to build and run on Eclipse 
=======================

Installing Eclipse 
==================
.. image:: ../../images/eclipse1.png
   :alt: Eclipse1 
   :target: https://www.eclipse.org/downloads/
   :class: with-shadow
   :scale: 100

First, you should download and install your favorite desktop IDE packages (links to the various Eclipse versions on the Eclipse website: https://www.eclipse.org/downloads/)


Once you have downloaded the installer, you can run Eclipse installer.

.. Note:: For more detailed approach visit https://www.eclipse.org/downloads/packages/installer



then select Eclipse IDE for Scientific Computing and install it:


.. image:: ../../images/eclipse2.png
   :alt: Eclipse2
   :align: center
   :class: with-shadow
   :scale: 80
   

Package Description:

           .. code-block:: console
		
	              	
                  Tools for C, C++, Fortran, and UPC, including MPI, OpenMP, OpenACC, a parallel debugger, and remotely building, running and monitoring applications.

                  This package includes:
                      C/C++ Development Tools
                      Git integration for Eclipse
                      Mylyn Task List
                      Parallel Tools Platform
                      Eclipse XML Editors and Tools	


Next, enter the work directory (your working directory) and clone the DEST code into a folder, e.g. DEST-master

    .. code-block:: console
		
		cd yourwork
                git clone https://gitlab.DEST_master 


After the code is cloned, enter your work folder, make a build directory outside DEST folder and enter it
    .. code-block:: console
		mkdir Build
		cd Build


From within the build directory, run the configure command (with updated path!). Note the use of CC and CXX to select the special compilers.

    .. code-block:: console
		
	cmake -G "Eclipse CDT4 - Ninja"   -DCMAKE_BUILD_TYPE:STRING="Debug" -DCMAKE_INSTALL_PREFIX:PATH="/home/kevinb/Videos/DEST-master/src/Install"  -DCMAKE_C_COMPILER="/usr/bin/cc"  -DCMAKE_CXX_COMPILER="/usr/bin/c++"  /home/kevinb/Videos/DEST-master/src/CMakeLists.txt
	
If configuring and generating using CMake were successful you will see something similar to the following:

.. image:: ../../images/eclipse3.png
   :alt: Eclipse3
   :align: center
   :class: with-shadow
   :scale: 80


At this point you can run cmake .. to e.g. disable unnecessary solvers, then run cmake as usual to build the code (with updated path!)

    .. code-block:: console
		
		cmake --build /home/kevinb/Videos/Build  --clean-first  --config Debug -- "-v"

Finally, if building using CMake was successful you will see something similar to the following:

.. image:: ../../images/eclipse4.png
   :alt: Eclipse4
   :align: center
   :class: with-shadow
   :scale: 80


Then check the executable file in ../DEST-master/src/BIN

    .. code-block:: console
    
		file DEST_analyser_Debug

For testing the executable file you can run the following:
    .. code-block:: console
		
		./DEST_analyser_Debug   -filename ../TESTS/B_013/B_013.dat
		
Now you can start Eclipse and select/create a directory as eclipse-workspace:	
    
.. image:: ../../images/eclipse5.png
   :alt: Eclipse5
   :align: center
   :class: with-shadow
   :scale: 90



How to build and run on CLion 
=======================

Currently the only IDE that can generate all three executables (DEST_analyser, DEST_optimiser and DEST_conveyor) for Windows. 

The "make" (as an older version of "cmake") approach to compiling and linking the code on all platforms should also work, but needs updating to ensure that is works (rather than just on Linux) on Windows and macOS. 	
