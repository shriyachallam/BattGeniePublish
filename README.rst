|docs|

.. inclusion-marker-do-not-remove
Note: This project is not currently being kept up to date, so opened issues may not be answered.
================================================================================================
Preparing MACCOR Data
======================

The **maccorcyclingdata** package is to be used on the raw data output from the `MACCOR`_ battery cyclers and the schedule file input into the `MACCOR`_ battery cyclers. The package can also be used to validate the testdata by comparing it against the schedules.

Example
-------

The **example.ipynb** provides examples where all the functions are used on the given example data. 
To run this example, simply open and run each cell in the example Jupyter Notebok provided.
In the ``example_data`` directory, there is example testdata and an example schedule file to show how the data columns should be formatted.

Requirements and Installation
-----------------------------

This code has been developed in Python 3.7.6. The code has been tested to run in Windows, Linux, and macOS. 

This code uses numpy and pandas as specified in docs/requirements.txt.

The code can be run directly from a cloned GitHub `repository`_ or it can also be installed as a python `package`_ through pip:

.. code::

   pip install maccorcyclingdata

The functions in the package can be used after importing testdata, schedules, validate for example as follows:

.. code-block:: python

   import maccorcyclingdata.testdata as testdata
   import maccorcyclingdata.schedules as schedules
   import maccorcyclingdata.validate as validate

.. _compability:

Compatibility
-------------

The raw testdata and schedule file that this package is used on must be csv files. Additionally, the first column of both files should be the header of the datatable.
The example uses data exported from `MACCOR`_ battery cyclers.
The raw testdata should be exported with columns in the following order and with the following units (the names can be anything since the **import_maccor_data** function will rename all columns):

#. Cycle Number

#. Step Number 

#. Total Test Time (seconds)

#. Step Time (seconds)

#. Capacity (mAh)

#. Current (mA)

#. Voltage (V)

#. DPt Time (seconds)

#. Temperature (Celsius)

#. EV Temperature (Celsius)

The following columns may also exist, but must be named as the following: ``ACR``, ``DCIR``, ``Watt-hr``, and ``nnnamed``. 

The schedule should have columns in the following order (the names can be anything since the **import_schedules** function will rename all columns):

#. Step Number

#. Step Type

#. Step Mode Type

#. Step Mode Value

#. Step Limit Type

#. Step Limit Value

#. End Type

#. Operator (=, <=, >=)

#. End Type Value

#. Goto Step Number

#. Report Type

#. Report Type Value

#. Options

#. Step Note

If you encounter any issues running the code for any MACCOR model report an issue. Note that an example file will be needed in order to improve the code.

.. _MACCOR: http://www.maccor.com/

.. _package: https://pypi.org/project/maccorcyclingdata/

.. _repository: https://github.com/shriyachallam/maccorcyclingdata

.. |docs| image:: https://readthedocs.org/projects/maccorcyclingdata/badge/?version=latest
    :target: https://maccorcyclingdata.readthedocs.io/en/latest/?badge=latest
    :alt: Documentation Status
