SParse Optimization Research COde (SPORCO)
==========================================


.. image:: https://travis-ci.org/bwohlberg/sporco.svg?branch=master
    :target: https://travis-ci.org/bwohlberg/sporco
    :alt: Build Status
.. image:: https://landscape.io/github/bwohlberg/sporco/master/landscape.svg?style=flat
   :target: https://landscape.io/github/bwohlberg/sporco/master
   :alt: Code Health
.. image:: https://readthedocs.org/projects/sporco/badge/?version=latest
    :target: http://sporco.readthedocs.io/en/latest/?badge=latest
    :alt: Documentation Status
.. image:: https://codecov.io/gh/bwohlberg/sporco/branch/master/graph/badge.svg
    :target: https://codecov.io/gh/bwohlberg/sporco
    :alt: Test Coverage
.. image:: https://badge.fury.io/py/sporco.svg
    :target: https://badge.fury.io/py/sporco
    :alt: PyPi Release
.. image:: https://img.shields.io/pypi/pyversions/sporco.svg
    :target: https://github.com/bwohlberg/sporco
    :alt: Supported Python Versions
.. image:: https://img.shields.io/pypi/l/sporco.svg
    :target: https://github.com/bwohlberg/sporco
    :alt: Package License
.. image:: http://mybinder.org/badge.svg
    :target: http://mybinder.org/repo/bwohlberg/sporco
    :alt: Binder


SPORCO is a Python package for solving optimisation problems with sparsity-inducing regularisation. These consist primarily of sparse coding and dictionary learning problems, including convolutional sparse coding and dictionary learning, but there is also support for other problems such as Total Variation regularisation and Robust PCA. In the current version all of the optimisation algorithms are based on the Alternating Direction Method of Multipliers (ADMM).


Documentation
-------------

Documentation is available online at `Read the Docs <http://sporco.rtfd.io/>`_ and `PyPI <http://pythonhosted.org/sporco/>`_, or can be built from the root directory of the source distribution by the command

::

   python setup.py build_sphinx

in which case the HTML documentation can be found in the ``build/sphinx/html`` directory (the top-level document is ``index.html``).


An overview of the package design and functionality is also available in

  Brendt Wohlberg, `SPORCO: A Python package for standard and convolutional sparse representations <http://conference.scipy.org/proceedings/scipy2017/brendt_wohlberg.html>`_, in Proceedings of the 15th Python in Science Conference, (Austin, TX, USA), pp. 1--8, Jul 2017


Usage
-----

Scripts illustrating usage of the package can be found in the ``examples`` directory of the source distribution. (Many of these examples require standard test images, the installation of which is described in section Test Images below.) These examples can be run from the root directory of the package by, for example

::

   python examples/stdsparse/demo_bpdn.py


To run these scripts prior to installing the package it will be necessary to first set the ``PYTHONPATH`` environment variable to include the root directory of the package. For example, in a ``bash`` shell

::

   export PYTHONPATH=$PYTHONPATH:`pwd`


from the root directory of the package.


`Jupyter Notebook <http://jupyter.org/>`_ versions of some of the demos in ``examples`` are also available in the same directories as the corresponding demo scripts. The scripts can also be viewed online via `nbviewer <https://nbviewer.jupyter.org/github/bwohlberg/sporco/blob/master/index.ipynb>`_, or run interactively at `binder <http://mybinder.org/repo/bwohlberg/sporco>`_ (but note that this `service <http://mybinder.org/status>`_ seems to be only intermittently functional).



Requirements
------------

The primary requirements are Python itself, and modules  `future <http://python-future.org>`_, `numpy <http://www.numpy.org>`_, `scipy <https://www.scipy.org>`_, `pyfftw <https://hgomersall.github.io/pyFFTW>`_, and `matplotlib <http://matplotlib.org>`_. Module `numexpr <https://github.com/pydata/numexpr>`_ is not required, but some functions will be faster if it is installed. If module `mpldatacursor <https://github.com/joferkington/mpldatacursor>`_ is installed, functions ``plot.plot`` and ``plot.imview`` will support the data cursor that it provides.

Instructions for installing these requirements are provided in the `Requirements <http://sporco.readthedocs.io/en/latest/install.html#requirements>`_ section of the package documentation.


Installation
------------

To install the most recent release of SPORCO from `PyPI <https://pypi.python.org/pypi/sporco/>`_ do

::

    pip install sporco


To install the development version from `GitHub <https://github.com/bwohlberg/sporco>`_ do

::

    git clone https://github.com/bwohlberg/sporco.git

followed by

::

   cd sporco
   python setup.py build
   python setup.py install

The install commands will usually have to be performed with root privileges.


A summary of the most significant changes between SPORCO releases can be found in the ``CHANGES.rst`` file. It is strongly recommended to consult this summary when updating from a previous version.



Test Images
-----------

The usage examples, described above, make use of a number of standard test images, which can be installed using the ``sporco_get_images`` script. To download these images from the root directory of the source distribition (i.e. prior to installation) do

::

   bin/sporco_get_images --libdest

after setting the ``PYTHONPATH`` environment variable as described below. To download the images as part of a package that has already been installed, do

::

  sporco_get_images --libdest

which will usually have to be performed with root privileges.


License
-------

This package is distributed with a 3-Clause BSD license; see the ``LICENSE`` file for details.
