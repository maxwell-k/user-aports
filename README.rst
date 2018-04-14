Building locally
----------------

#.  Enter a new Alpine Linux ``chroot``, with Ansible installed and acquire
    ``root``
#.  Clone this repository to ``/builds/keith.maxwell/aports`` and move there

    ..
        mkdir /builds /builds/keith.maxwell /builds/keith.maxwell/aports &&
        cd /builds/keith.maxwell/aports &&
        git clone https://gitlab.com/keith.maxwell/aports .

#.  Add the private key as ``keith.maxwell@gmail.com-5a1151a5.rsa``
#.  Install build tools with ``./setup.yaml``
#.  Build with ``su abuild -c 'buildrepo local'``

Main repository
---------------

To get a copy of the main Alpine Linux repository use::

    git clone --depth 1 git://git.alpinelinux.org/aports

Resources
---------

A sample_ `APKBUILD` is available:

.. code:: sh

    curl -o APKBUILD \
        https://git.alpinelinux.org/cgit/abuild/plain/sample.APKBUILD

The `APKBUILD Reference`_ is a wiki page

.. _sample: https://git.alpinelinux.org/cgit/abuild/log/sample.APKBUILD
.. _APKBUILD Reference: https://wiki.alpinelinux.org/wiki/APKBUILD_Reference

.. vim: ft=rst
