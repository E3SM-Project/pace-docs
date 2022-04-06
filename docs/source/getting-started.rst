Getting-Started-Upload
=====

First, download the pace upload client and run the client to upload experiments to PACE.

.. note::

   The experiments ran on supercomputers are automatically uploaded to the PACE.

.. _tool:

Tool
------------

Please download and use this tool: 
`Python 3 version <https://pace.ornl.gov/static/tools/pace-upload3>`_ 
or 
`Python 2 version <https://pace.ornl.gov/static/tools/pace-upload>`_
to upload experiment data directly from supercomputers.

To download using command line:

Python 2 version

.. code-block:: console

   $ wget https://pace.ornl.gov/static/tools/pace-upload
   $ chmod +x ./pace-upload

Python 3 version

.. code-block:: console

   $ wget https://pace.ornl.gov/static/tools/pace-upload3
   $ chmod +x ./pace-upload3

This is a Python-based tool that can be executed directly (./pace-upload) 
once you download and make it executable. 
The system-wide Python 2.x installation on Summit/Theta/Cori/Compy has the 
requisite 'requests' module to enable this tool to work.
It presently handles uploading user data in performance archive directories from 
all E3SM supported machines. The server checks for duplicates while processing uploaded data.

Please `see the demo <https://www.youtube.com/watch?v=Vd3q3mJPQFs>`_ for reference. A log file is written at the end that details the upload progress and notes any errors.

Usage
----------------

Example:

.. code-block:: console

   $ ./pace-upload --perf-archive user-exps-set

Detailed usage:

.. code-block:: console
   
   $ ./pace-upload --help
   usage: pace-upload [-h] [--exp-dir SOURCE] [--perf-archive SOURCE]
                   [--application {e3sm}]
   PACE upload tool.
   optional arguments:
      -h, --help            show this help message and exit
      --exp-dir SOURCE, -ed SOURCE
                              Root directory containing experiment(s) results.
                              Handles multiple experiment directories under root
      --perf-archive SOURCE, -pa SOURCE
                              Root directory containing performance archive. Handles
                              multiple performance archive directories under root
      --application {e3sm}, -a {e3sm}
                              Application name

