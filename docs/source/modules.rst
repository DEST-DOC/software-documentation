.. _modules:

.. modules
.. ============

Modules 
===================

DEST is designed and implemented as a modular system in order to accommodate further additions and/or improvements to the currently available modelling techniques.  The implementation employs structured and object-oriented approaches to data management, fast memory access as well as vector and parallel processing technologies thus enabling rapid turnaround of numerical simulations comprised within computer aided engineering tasks. 

 
This modularity starts from grouping the overall functionality into these key modules (each module should create a library upon compilation) 

UTIL - fundamental library that provides interfaces to different computing platforms (Linux, Windows, macOS, etc.) 

Note that some header files simply provide "redirection" to equivalent header files in various default folders on different platforms 

Please make sure that anything platform dependent which you encounter during the development is discussed with the aim to implement such fundamental, platform dependent, functionality in this folder 

UI - another fundamental library that provides the platform dependent functionality for Graphical User Interface that enables DEST_conveyor to appear on the screen and perform its functionality.  The underlying enabling library is Tcl/Tk.  This is one of DEST's vulnerabilities, as maintaining this functionality depends upon the availability and further development of the Tcl/Tk software which is being constantly being super-seeded by python or the availability of generic pre-post/processors such as GMESH and ParaView. 

DBASE - this module is responsible for structing the memory and for input/output functionality that fills that memory from input data file, as well as outputs from that memory into output files - see:  Data flow 

MESHGEN 

DOMDEC 

ANALYSER - This is, currently, an explicit DEM/FEM solver for direct modelling. 

OPTIMISER - A simple optimisation package designed to run simultaneously many DEST_analyser runs and vary parameters that are labelled in all .dat files for the DEST_analyser runs in the same optimisation run.  Objective functions can be provided in different ways, as per documentation.  This is an inverse modelling tool. 

CONVEYOR - GUI and "integration platform", designed to work closely with DEST_analysers and DEST_optimiser, but also to help with various interfacing and automation tasks. 

DARCoMS - The Dynamic Adaptive Recursive Concurrent Multiscale Supermodule that calls upon DEST capability to run multiscale problems. Current implementation focuses on the Multi Timestep Integration (Subcycling) of subdomains

The above is a "bottom-up" description, in terms of dependencies, but the interdependencies are sometimes a bit more complex than the above list suggests, though every effort should be made to keep the interdependencies as simple as possible. 


