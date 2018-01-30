Electrum BCD - Lightweight Bitcoin Diamond client
=====================================

::

  Licence: MIT Licence
  Author: BCD Developer
  Language: Python
  Homepage: https://github.com/eveybcd/electrum



Getting started
===============

Electrum BCD is a pure python application. If you want to use the
Qt interface, install the Qt dependencies::

    sudo apt-get install python3-pyqt5

If you downloaded the official package (tar.gz), you can run
Electrum BCD from its root directory, without installing it on your
system; all the python dependencies are included in the 'packages'
directory. To run Electrum from its root directory, just do::

    ./electrum

You can also install Electrum BCD on your system, by running this command::

    sudo apt-get install python3-setuptools
    python3 setup.py install

This will download and install the Python dependencies used by
Electrum BCD, instead of using the 'packages' directory.

If you cloned the git repository, you need to compile extra files
before you can run Electrum BCD. Read the next section, "Development
Version".



Development version
===================

Check out the code from Github::

    git clone git://github.com/eveybcd/electrum.git
    cd electrum

Run install (this should install dependencies)::

    python3 setup.py install

Compile the icons file for Qt::

    sudo apt-get install pyqt5-dev-tools
    pyrcc5 icons.qrc -o gui/qt/icons_rc.py

Compile the protobuf description file::

    sudo apt-get install protobuf-compiler
    protoc --proto_path=lib/ --python_out=lib/ lib/paymentrequest.proto

Create translations (optional)::

    sudo apt-get install python-pycurl gettext
    ./contrib/make_locale




Creating Binaries
=================


To create binaries, create the 'packages' directory::

    ./contrib/make_packages

This directory contains the python dependencies used by Electrum.

Mac OS X / macOS
--------

::

    ./contrib/freeze_packages.sh
    ./contrib/make_osx

Windows
-------

See `contrib/build-wine/README` file.


Android
-------

See `gui/kivy/Readme.txt` file.
