.. _execution:

DEST is designed and implemented as a modular system in order to accommodate further additions and/or improvements to the currently available modelling techniques.  The implementation employs structured and object-oriented approaches to data management, fast memory access as well as vector and parallel processing technologies thus enabling rapid turnaround of numerical simulations comprised within computer aided engineering tasks. 

 

This modularity starts from grouping the overall functionality into just three executables: 

DEST_analyser, standalone (GUI-less) Analyser module for direct modelling 

DEST_optimiser, standalone (GUI-less) Optimiser module for inverse modelling 

DEST_conveyor, Graphical User Interface (GUI) to Modeller, Analyser/Optimiser and Reporter modules, in which the Analyser and Optimiser modules incorporate full functionality of standalone DEST_analyser and DEST_optmiser executables 

 

Launching executables and command line options: 

DEST_analyser 

 

DEST_anayser can be started by double clicking on the program icon in the file manager or by typing the program name (DEST_anayser_RELEASE_* or DEST_anayser_DEBUG_*) on terminal’s command line.  

 

Command line options syntax: 

-filename 

The keyword preceding the direct modelling data file name. 

-logdir 

The keyword preceding the log directory name.  The default location of the log file is user’s home directory on Unix systems and the root directory of the current hard disk on MS-Windows system.  The default location of the log file can be specified by setting the environment variable DEST_LOG to the desired log file name. 

-help 

The keyword causing brief information on the available command line options to be displayed. 

-debug 

The keyword that announces the following debugging options (available in DEBUG mode only) 

ALL 

FILE sourcefilename 

FUNC functionname 

FLOW 

DUMP 

TIMES 

 

The above tabulated command line options can be obtained by typing "-help" after the program name (as illustrated below) or by simply mistyping any of the command line options. 

 

Examples:  

  DEST_analyser_RELEASE_Win32.exe -filename tests/example001.dat -logdir tests/logdir 

  DEST_analyser_RELEASE_Linux –filename tests/bars/bar1.dat -logdir tests/logdir 

  DEST_analyser_DEBUG_IRIX64 -filename tests/bars/bar1.dat -logdir tests/logdir -debug FILE solveq.c FUNC F_asseld FLOW TIMES 
  DEST_analyser_DEBUG_Win32.exe -filename C:\Users\nikpe\REP\DEST-1\TESTS\NEW\KFC\B_0230.dat -logdir C:\Users\nikpe\REP\DEST-1\TESTS\NEW\KFC -debug ALL FLOW TIMES 
 

 

DEST_optimiser 

DEST_optimiser_RELEASE_Win32.exe -optfilename tests/example071.opt -logdir tests/logdir 

 

DEST_conveyor 

 

DEST_conveyor can be started by double clicking on the program icon in the file manager or by typing the program name (DEST_conveyor_RELEASE_* or DEST_conveyor_DEBUG_*) on terminal’s command line.  

 

Command line options syntax: 

-filename 

The keyword preceding the direct modelling data file name. 

-optfilename 

The keyword preceding the inverse modelling data file name. 

-logdir 

The keyword preceding the log directory name.  The default location of the log file is user’s home directory on Unix systems and the root directory of the current hard disk on MS-Windows system.  The default location of the log file can be specified by setting the environment variable DEST_LOG to the desired log file name. 

-help 

The keyword causing brief information on the available command line options to be displayed. 

-debug 

The keyword that announces the following debugging options (available in DEBUG mode only) 

ALL 

FILE sourcefilename 

FUNC functionname 

FLOW 

DUMP 

TIMES 

 

The above tabulated command line options can be obtained by typing "-help" after the program name (as illustrated below) or by simply mistyping any of the command line options. 

 

Examples:  

  DEST_conveyor_RELEASE_Win32.exe -filename tests/example001.dat -logdir tests/logdir 

  DEST_conveyor_RELEASE_Win32.exe -optfilename tests/example071.opt -logdir tests/logdir 

  DEST_conveyor_RELEASE_Linux –filename tests/bars/bar1.dat -logdir tests/logdir 

  DEST_conveyor_DEBUG_IRIX64 -filename tests/bars/bar1.dat -logdir tests/logdir -debug FILE,solveq.c,FUNC,F_asseld FLOW TIMES 
