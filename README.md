# SrvStart
This repository contains the legacy code I wrote for SrvStart in 2000, along with some related software.
SrvStart allows you to run an ordinary Windows executable as a Windows service.

# Help and Support
I no longer provide support for SrvStart -
I am a [software architect](https://www.viewpoints-and-perspectives.info) these days.
Also, I no longer have access to a Windows / .NET build and test environment.

You should find the answers to most questions in the documentation in this repository.
In particular, please read the **SrvStart FAQ** (`srvstart/doc/services-faq.pdf`) for instructions on how to get yourself up and running with SrvStart.

## Supported Operating Systems
I originally wrote SrvStart for Windows NT 4 - yes, that's how old it is!
However I have been told that the software works for all subsequent versions of Windows,
up to and including Windows 10.

## Warning
Modify Windows NT service settings at your own peril. Making incorrect changes can render Windows unuseable.

**_If you don't know what you are doing, don't mess about with services!_**

# Overview

## Problem Statement
I originally wrote SrvStart because I wanted to be able to run the Sybase RDBMS server as a Windows NT service,
and it didn't have native support for that.
Running a program as a Windows NT service means it can be configured to start automatically in the background when Windows starts up,
to restart if it crashes, and to run as a specific user or as the special NT user `LocalSystem`.

## SrvStart Components
There are four components to SrvStart.

1. **SrvStart** itself. This comprises an executable program and a configuration file.
   It is a mandatory component.
1. **Logger**. This is a DLL that SrvStart uses to log error messages.
   It is a mandatory component.
1. **`MSVCRT.DLL`**. This is the Microsoft Visual C++ runtime.
   It is an old version that worked with my programs.
   You may be able to use a newer version.
1. **`SVC.EXE`**. This is a program that you can use to install services.
   (You can also use SrvStart itself to install a service.
   There are better alternatives available nowadays, free or paid-for, if you need more flexibility.)

## Artefacts in This Repository
This repository contains the following artefacts for each component:

1. Run-time artefacts (programs and executables) in the file **_`<component>`_`_run.zip`**.
1. Documentation in the file **_`<component>`_`_doc.zip`**.
1. Complete source code in the file **_`<component>`_`_src.zip`**. The components are written in C++.
1. Build artefacts in the file **_`<component>`_`_bld.zip`**.

# Getting Started
1. Install the necessary executables and DLLs.
1. Create a service configuration file with information on the program you want to run.
1. Install the Windows service.
1. Start the service.

Full  instructions are given in the SrvStart FAQ (`srvstart/doc/services-faq.pdf`).

## Documentation
Detailed program and API documentation can be found in `srvstart/doc/services.pdf`.

# Rebuilding the Software
You don't need to build the software to use it - you should be able to install the existing software components as described in the FAQ.

I don't think the software will build in modern versions of Visual C++ without modification.
If you want to make any changes to it, you will need to set up your own build environment.

# Licence and Warranty
SrvStart, Logger and `SVC.EXE` are all Copyright (C) 1998 - 2018 Nick Rozanski.

The software is Free software.
You can redistribute it and/or modify it, under the terms of the GNU Lesser General Public License, as published by the Free Software Foundation);
either version 2 of the License, or (at your option) any later version.

It goes without saying that this software is distributed in the hope that it will be useful, but without any warranty;
without even the implied warranty of merchantability or fitness for a particular purpose.

