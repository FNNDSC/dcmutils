##############
pfdcm  v0.99.3
##############

.. image:: https://badge.fury.io/py/pfdcm.svg
    :target: https://badge.fury.io/py/pfdcm

.. image:: https://travis-ci.org/FNNDSC/pfdcm.svg?branch=master
    :target: https://travis-ci.org/FNNDSC/pfdcm

.. image:: https://img.shields.io/badge/python-3.5%2B-blue.svg
    :target: https://badge.fury.io/py/pfdcm

.. contents:: Table of Contents

********
Overview
********

This repository provides ``pfdcm`` -- a controlling service that speaks to a PACS and handles DICOM data management.

pfdcm
=====

Most simply, ``pfdcm`` provides a REST-type interface to querying a PACS as well as managing DICOM data received from a PACS.

************
Installation
************

Installation is relatively straightforward, and we recommend using either python virtual environments or docker.

Python Virtual Environment
==========================

On Ubuntu, install the Python virtual environment creator

.. code-block:: bash

  sudo apt install virtualenv

Then, create a directory for your virtual environments e.g.:

.. code-block:: bash

  mkdir ~/python-envs

You might want to add to your .bashrc file these two lines:

.. code-block:: bash

    export WORKON_HOME=~/python-envs
    source /usr/local/bin/virtualenvwrapper.sh

Then you can source your .bashrc and create a new Python3 virtual environment:

.. code-block:: bash

    source .bashrc
    mkvirtualenv --python=python3 python_env

To activate or "enter" the virtual env:

.. code-block:: bash

    workon python_env

To deactivate virtual env:

.. code-block:: bash

    deactivate

Using the ``fnndsc/ubuntu-python3`` dock
========================================

We provide a slim docker image with python3 based off Ubuntu. If you want to play inside this dock and install ``pman`` manually, do

.. code-block:: bash

    docker pull fnndsc/ubuntu-python3

This docker has an entry point ``python3``. To enter the dock at a different entry and install your own stuff:

.. code-block:: bash

   docker run -ti --entrypoint /bin/bash fnndsc/ubuntu-python3
   
Now, 

.. code-block:: bash

   apt update && \
   apt install -y libssl-dev libcurl4-openssl-dev librtmp-dev && \
   pip install pfdcm
   
**If you do the above, remember to** ``commit`` **your changes to the docker image otherwise they'll be lost when you remove the dock instance!**

.. code-block:: bash

  docker commit <container-ID> local/ubuntu-python3-pfdcm
  
 where ``<container-ID>`` is the ID of the above container.
  

Using the ``fnndsc/pfdcm`` dock
===============================

The easiest option however, is to just use the ``fnndsc/pfdcm`` dock.

.. code-block:: bash

    docker pull fnndsc/pfdcm
    
and then run

.. code-block:: bash

    docker run --name pfdcm -v /home:/Users --rm -ti fnndsc/pfdcm --forever --httpResponse

*****
Usage
*****

For usage of  ``pfdcm``, consult the relevant wiki pages.

``pfdcm`` usage
===============

For ``pfdcm`` detailed information, see the `pfdcm wiki page <https://github.com/FNNDSC/pfdcm/wiki/pfdcm-overview>`_.




