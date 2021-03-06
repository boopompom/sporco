Installation
============

The simplest way to install the most recent release of SPORCO from
`PyPI <https://pypi.python.org/pypi/sporco/>`_ is

::

    pip install sporco


SPORCO can also be installed from source, either from the development
version from `GitHub <https://github.com/bwohlberg/sporco>`_, or from
a release source package downloaded from `PyPI
<https://pypi.python.org/pypi/sporco/>`_.

To install the development version from `GitHub
<https://github.com/bwohlberg/sporco>`_ do

::

    git clone https://github.com/bwohlberg/sporco.git

followed by

::

   cd sporco
   python setup.py build
   python setup.py test
   python setup.py install

Please report any test failures. The install command will usually have to be performed with root permissions, e.g. on Ubuntu Linux

::

   sudo python setup.py install

The procedure for installing from a source package downloaded from `PyPI
<https://pypi.python.org/pypi/sporco/>`_ is similar.


A summary of the most significant changes between SPORCO releases can
be found in the ``CHANGES.rst`` file. It is strongly recommended to
consult this summary when updating from a previous version.



Test Images
-----------

The :ref:`usage examples <usage-section>` make use of a number of
standard test images, which can be installed using the
``sporco_get_images`` script. To download these images from the root
directory of the source distribution (i.e. prior to installation) do

::

   bin/sporco_get_images --libdest

after setting the ``PYTHONPATH`` environment variable as described in
:ref:`example-scripts-section`.  To download the images as part of a
package that has already been installed, do

::

  sporco_get_images --libdest

which will usually have to be performed with root privileges.



Requirements
------------

The primary requirements are Python itself, and modules `future
<http://python-future.org>`_, `numpy
<http://www.numpy.org>`_, `scipy <https://www.scipy.org>`_, `pyfftw
<https://hgomersall.github.io/pyFFTW>`_, and `matplotlib
<http://matplotlib.org>`_. Module `numexpr
<https://github.com/pydata/numexpr>`_ is not required, but some
functions will be faster if it is installed. If module `mpldatacursor
<https://github.com/joferkington/mpldatacursor>`_ is installed, functions
:func:`.plot.plot` and :func:`.plot.imview` will support the data cursor that it provides.


Installation of these requirements is system dependent.

.. tabs::

   .. group-tab:: :fa:`linux` Linux

      Under Ubuntu Linux 16.04, the following commands should be sufficient for Python 2

      ::

	sudo apt-get install python-numpy python-scipy python-numexpr
	sudo apt-get install python-matplotlib python-pip python-future
	sudo apt-get install libfftw3-dev python-pytest
	sudo -H pip install pyfftw pytest-runner

      or Python 3

      ::

	sudo apt-get install python3-numpy python3-scipy python3-numexpr
	sudo apt-get install python3-matplotlib python3-pip python3-future
	sudo apt-get install libfftw3-dev python3-pytest
	sudo -H pip3 install pyfftw pytest-runner

      For some versions of SciPy it might also be necessary to install `Pillow <https://python-pillow.org/>`_

      ::

	sudo -H pip3 install pillow


      Some additional dependencies are required for building the
      documentation from the package source. For example, under Ubuntu
      Linux 16.04, the following commands should be sufficient for Python 2

      ::

	sudo apt-get install python-sphinx python-numpydoc
	sudo -H pip install sphinxcontrib-bibtex sphinx_tabs sphinx_fontawesome

      or Python 3

      ::

	sudo apt-get install python3-sphinx python3-numpydoc
	sudo -H pip3 install sphinxcontrib-bibtex sphinx_tabs sphinx_fontawesome


   .. group-tab:: :fa:`apple` Mac OS

      The first step is to install Python 2.7

      ::

	brew install python

      or the current version of Python 3.x

      ::

	brew install python3

      The `FFTW library <http://www.fftw.org/>`_ is also required

      ::

	brew install fftw


      The Python modules required by SPORCO can be installed using `pip`

      ::

	pip install numpy scipy Pillow matplotlib pyfftw
	pip install six future subprocess functools python-dateutil
	pip install pyparsing cycler pytz pytest pytest-runner

      (For Python 3, replace `pip` above with `pip3`.)


      Some additional dependencies are required for building the
      documentation from the package source

      ::

	pip install sphinx numpydoc sphinxcontrib-bibtex sphinx_tabs
	pip install sphinx_fontawesome

      (For Python 3, replace `pip` above with `pip3`.)


   .. group-tab:: :fa:`windows` Windows

      A version of Python that includes NumPy and SciPy
      is required. The instructions given here are for installing a
      reference version from `python.org
      <https://www.python.org/downloads/windows/>`_, but a potentially
      simpler alternative would be to install one of the Windows
      versions of Python distributed with the SciPy stack that are
      listed at `scipy.org <https://scipy.org/install.html>`_.

      The first step is to install Python itself, e.g. for version
      3.6.2, download `python-3.6.2-amd64.exe
      <https://www.python.org/ftp/python/3.6.2/python-3.6.2-amd64.exe>`_
      and run the graphical installer. The easiest way of installing
      the main required packages is to download the binaries from the
      list of `Unofficial Windows Binaries for Python Extension
      Packages <http://www.lfd.uci.edu/~gohlke/pythonlibs/>`_. At the
      time of writing this documentation, the current versions of
      these binaries for each main package are

	* `NumPy <http://www.lfd.uci.edu/~gohlke/pythonlibs/tuft5p8b/numpy-1.13.1+mkl-cp36-cp36m-win_amd64.whl>`__
	* `SciPy <http://www.lfd.uci.edu/~gohlke/pythonlibs/tuft5p8b/scipy-0.19.1-cp36-cp36m-win_amd64.whl>`__
	* `Matplotlib <http://www.lfd.uci.edu/~gohlke/pythonlibs/tuft5p8b/matplotlib-2.0.2-cp36-cp36m-win_amd64.whl>`__
	* `pyFFTW <http://www.lfd.uci.edu/~gohlke/pythonlibs/tuft5p8b/pyFFTW-0.10.4-cp36-cp36m-win_amd64.whl>`__

      After downloading and saving each of these binaries, open a
      Command Prompt, change directory to the folder in which the
      binaries were saved, and enter

      ::

	pip install numpy-1.13.1+mkl-cp36-cp36m-win_amd64.whl
	pip install scipy-0.19.1-cp36-cp36m-win_amd64.whl
	pip install matplotlib-2.0.2-cp36-cp36m-win_amd64.whl
	pip install pyFFTW-0.10.4-cp36-cp36m-win_amd64.whl
	pip install future Pillow


      Some additional dependencies are required for building the
      documentation from the package source

      ::

	pip install sphinx numpydoc sphinxcontrib-bibtex sphinx_tabs
	pip install sphinx_fontawesome


      It is also necessary to download and install
      `Graphviz <http://www.graphviz.org/Download_windows.php>`__ and then
      set the Windows ``PATH`` environment variable to include the ``dot``
      command, e.g. to do this on the command line, for the current version
      of Graphviz

      ::

	set PATH=%PATH%;"C:\Program Files (x86)\Graphviz2.38\bin"
