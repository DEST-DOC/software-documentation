.. _execution:

This document briefly details how user/developers can set up a remote/local machine for job run/submission.

How to run using Visual Studio 
=======================

Currently the only IDE that can generate all three executables (DEST_analyser, DEST_optimiser and DEST_conveyor) for Windows. 

The "make" (as an older version of "cmake") approach to compiling and linking the code on all platforms should also work, but needs updating to ensure that is works (rather than just on Linux) on Windows and macOS. 	




Run using Visual Studio Code 
=====================

Visual Studio Code download 


Visual Studio Code Docs Documentation for Visual Studio Code, including Getting Started videos Visual Studio Code Introductory Videos 


Open DEST repository (http://isml-grs.eng.ox.ac.uk:8000) 



Run on macOS
=====================

Requirement: 

Add public ssh key to Gitlab server 

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" 

brew update 

brew install llvm libomp 

brew install cmake 

Git clone "http://isml-grs.eng.ox.ac.uk:8000/DEST/DEST.git"  

 

Compile 

cd DEST/BIN 

cmake -DCMAKE_C_COMPILER="/usr/local/opt/llvm/bin/clang" -DCMAKE_CXX_COMPILER="/usr/local/opt/llvm/bin/clang++" .. 

make -j 12 

 

Test  

./ANALYSER_ -filename ../TESTS/B_005/B_005.dat 
