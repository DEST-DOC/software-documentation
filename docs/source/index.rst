.. DEST documentation master file, created by
   sphinx-quickstart on Fri Mar 19 10:32:30 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to DEST's documentation!
=================================

What is DEST?  DEST stands for Discrete Elements Simulation Tools, where "discrete" refers to "distinct" or "geometrically separate", in the context of multi-body solid mechanics. 

 

At the moment, DEST is still very much just focused on mechanical analysis of multi-body interaction, such that it is capable of simulating the (thermo-)mechanical consequences of collision between distinct (or "discrete") bodies, approximated by either rigid (mathematically simple shapes, such as spheres) or deformable (approximated by discretisation into finite elements), while relying upon the leap frog finite difference stepping in time domain to solve the underlying PDEs, as the governing equations of this class of problems in mechanics.  BUT, the modular structure of the code allows it to grow, practically, without any limits, other than those define by the size of the computers on which it is used. 

 

So far, DEST served the purpose of helping the key elements of "computational mechanics" being presented to the members of the research team, all of whom contributed to DEST's growth, such that it became a form of our "knowledgebase", alongside the equipment which accumulated in the laboratory, where we execute the experiments that we aim to simulate using DEST. 

 

The "beauty" of DEST is in its openness and complete transparency shared by all of its developers, which means that those who contributed to its development are not restricted from taking it with them, if/when they leave the team, or continuing to stay connected to the core development team.  The plan is to extend this into OpenSource community, thus enabling more people to contribute/benefit by engaging with us. 

 

At the same time, building a database of results of experiments and the corresponding simulations should enable contributors and users to learn faster and store more valuable data/results into the database, thus helping to build this knowledgebase on the rate dependent behaviour of materials (our research "niche") faster/bigger. 

.. toctree::
   :caption: Installation and build
   :maxdepth: 1

   installation

.. toctree::
   :caption: FabNEPTUNE Workflow 
   :maxdepth: 1

   workflow

.. toctree::
   :caption: Execution
   :maxdepth: 1

   execution


