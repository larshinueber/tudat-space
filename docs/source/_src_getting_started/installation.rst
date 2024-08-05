
.. _getting_started_installation:

******************************
Installation
******************************

.. contents:: Content of this page
   :local:

This page will guide you through the installation of Tudat(Py). The installation is supported exclusively through the use of a ``conda``
package manager, such as Miniconda or Anaconda. For new users, and Windows users in particular, we recommend the use of `Anaconda`_ . 
For those with limited bandwidth or hard drive storage, we recommend the use of `Miniconda`_ (see also `Anaconda or Miniconda?`_). When referring to a ``conda`` package manager below,
the term "Anaconda" will be used. 

For more details on how to use ``conda``, please refer to our detailed guide (:ref:`getting_started_with_conda`) and the references therein.


.. _`Miniconda`: https://docs.conda.io/en/latest/miniconda.html
.. _`Anaconda`: https://docs.anaconda.com/navigator
.. _`Anaconda or Miniconda?`: https://docs.conda.io/projects/conda/en/latest/user-guide/install/download.html#anaconda-or-miniconda


Installing Anaconda/Miniconda
#############################

To install Anaconda or Miniconda on your system, see the `Anaconda Installation`_  of `Miniconda Installation`_ guide provided in their documentation

.. _`Anaconda Installation`: https://docs.anaconda.com/anaconda/install/
.. _`Miniconda Installation`: https://docs.conda.io/en/latest/miniconda.html



Installing Tudat(Py)
####################

.. attention::

  As of TudatPy version 0.7, a number of modifications have been made to how TudatPy deals with vehicle orientations,
  in particular in the context of thrust and aerodynamic guidance. These changes are, in part, not backwards compatible.
  See :ref:`this page <backwards_incompatibility>` for more details. To continue to use the last older version of Tudat, install
  version 0.6.3.

To install Tudat(Py), we recommend the use of a terminal (command line) interface. On Unix system (Linux and Mac), ``conda`` should already be available within the terminal; you can open your terminal directly. On Windows, you can find a program called ``Anaconda Prompt`` in the Windows search. Using ``conda`` in the ``Anaconda Prompt`` is equivalent to the terminal use of ``conda`` on Unix. Some Unix commands are made available in this prompt, although most usage is equivalent to the Windows shell (see below for some useful terminal commands).

Open a terminal. Then first verify that ``conda`` is installed by executing the following command:

.. code-block::

    conda --version

Next ensure that ``conda`` is up-to-date.

.. code:: bash

    conda update conda

Download this ``environment.yaml`` (:download:`yaml <_static/environment.yaml>`). Then, in your terminal navigate to the directory containing this file and execute the following command (see below for tips on using the command line):

.. code:: bash

    conda env create -f environment.yaml

With the ``conda`` environment now installed, you can activate it to work in it using:

.. code:: bash

        conda activate tudat-space

.. note::
    At this point, you may choose to install the **development version of TudatPy**, which is a conda package that is updated as soon as changes are merged to the development branch of the code on GitHub. 
    To do so, you can run the following command:

    .. code:: bash

        conda install -c tudat-team/label/dev tudat
        conda install -c tudat-team/label/dev tudatpy


Congratulations! You have now installed Tudat and TudatPy and are ready to start running your simulations and analyses! We recommend you get started by having a look at our :ref:`getting_started_examples`.

If there are any issues with the installation process, please submit an issue on the `tudatpy-feedstock`_. If there are issues running examples, please submit an issue on the `tudatpy`_ repository.

.. _`tudatpy-feedstock`: https://github.com/tudat-team/tudatpy-feedstock
.. _`tudatpy`: https://github.com/tudat-team/tudatpy

.. note::

    **New to the command-line?** The following commands may be useful to you:

    +-------------------------------------------------------+--------------------------+-----------------------+
    | **Command effect**                                    | **Unix (Linux & macOS)** | **Windows**           |
    +-------------------------------------------------------+--------------------------+-----------------------+
    | Enter a directory using a path (relative or absolute) | ``cd <abs/rel path>``    | ``cd <abs/rel path>`` |
    +-------------------------------------------------------+--------------------------+-----------------------+
    | Go back to the parent directory                       | ``cd ..``                | ``cd ..``             |
    +-------------------------------------------------------+--------------------------+-----------------------+
    | List the contents of the current working directory    | ``ls``                   | ``dir``               |
    +-------------------------------------------------------+--------------------------+-----------------------+

    For more help on getting started with the command-line interface (CLI), you could start with a `tutorial`_.

.. _`tutorial`: https://blog.balthazar-rouberol.com/discovering-the-terminal

Updating Tudat(Py)
##################

To update an existing installation of ``tudatpy``, activate your ``tudat-space`` environment:

    .. code:: bash

        conda activate tudat-space

Then execute the following command to install the latest version of ``tudatpy``:

    .. code:: bash

        conda install -c tudat-team tudatpy

Note that using this command may also update additional packages (such as ``tudat``) that are needed to run the latest version of ``tudatpy``.


.. warning::

    It can happen that running the install command above does not update ``tudatpy`` to the latest version (which can be checked on the `Anaconda website <https://anaconda.org/tudat-team/tudatpy>`_). In that case it is recommended to execute the following command (while still in the ``tudat-space`` environment):

       .. code:: bash

           conda install --update-deps -c tudat-team tudatpy
           
Building your own TudatPy kernel
################################

If you would prefer to not use a conda package, but instead build your own tudatpy kernel from the source code, clone the ``tudat-bundle`` repository from `here <https://github.com/tudat-team/tudat-bundle>`_ and follow the instructions in the README. To build the latest version of the kernel, switch both the tudat and tudatpy repositories to the ``master`` branch in step 3 of the README. To build the ``\dev`` version, use both repositories to the ``develop`` branch.

.. note::

    This workflow is not recommended for new users










