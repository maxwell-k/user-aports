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

.. vim: ft=rst
