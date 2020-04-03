.. _why-dripline:

=================
Why Use Dripline?
=================

Dripline is a framework for monitoring and controls systems aimed at small-to-medium-scale experimental setups.  It can monitor and control diverse pieces of hardware and software in a distributed, flexible way.
​
If you've reached this page, you are probably asking why you would consider using dripline 
and if it is an appropriate solution for your problem.
The answer to both will depend on circumstances, and we'll try and dig into that a bit.

You should consider using dripline if:
​
#. Your system under control is continuously evolving
#. You require flexible controls that will support operational modes that you can't clearly define from the start
#. You need to support continuous operation of part of your system while developing or updating another
#. You need support for multiple users interacting with the system at the same time, over remote connections, possibly with slow or unstable network interfaces
#. You need controls that are distributed and coordinated across multiple servers
#. Your equipment supports a well-documented control interface and communication protocol and/or provides linux-compatible drivers and libraries
#. You want to be able to easily add arbitrary coordination logic implemented in python
#. You want to be able to implement performant components in C++
#. You are comfortable working in a linux environment and from the command line
#. Your system needs to operate continuously and will combine equipment and subsystems that are quite different from each other
​
You should consider not using dripline if:

#. You need a system to operate on an open network and expect it to maintain strict security
#. Your system uses a very small number of devices and/or devices that are very similar or from a single OEM that provides a control solution
#. Your equipment is easily controlled as a monolithic unit and from a single server
#. The primary role of your control system is providing a local graphical interface for a user to work with the system interactively
#. The control interface to your equipment uses closed-source/proprietary drivers that are specific to another control system and/or incompatible with modern linux.


If you're interested in learning more aboout dripline, or using it for your system, 
please :ref:`let us know <contact-us>`!
​
​
Why We Built Dripline
=====================
​
Dripline was designed and built by the `Project 8 <http://www.project8.org>`_ collaboration, as the slow-controls system for a small-but-growing physics experiment. 
At the time that Project 8 was starting (in the early 2010s), the available experimental control systems had a major gap.
Some solutions were quite capable, but were built around a single application running on a single server and operating everything.
Many available options were also only available on closed-source operating systems, which added cost and licensing burdens both on the main system, and reduced the possibility of parallel development.
Open-source solutions existed, developed for larger physics collaborations, but these were all focused on projects that were large enough to have dedicated support personnel, and required developing in large codebases that needed a significant onboarding effort.
​
Dripline was designed based on inspiration from the RESTful interfaces and the growth of cloud-based computing paradigms.
It focuses on first building a framework that is modular, and then provides useful components to plug into that framework.
This allows the system to grow and evolve in an incremental way, adding new features as they are needed.
It also allows a control system to leverage the powerful support applications that are developed by the vast cloud-computing industry.
Finally, we wanted a system that supported very simple expansion with minimal effort when new components are familiar (often you add a configuration file of less than 100 lines, describing a new device), very complicated logic when required (you can easily connect any component you may write in python or C++), and which was fully version controllable so that there should not be hidden configuration information required to re-provision a system.
