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

Ideas
-----

-   `jpeginfo <https://github.com/tjko/jpeginfo>`__,
    a simple C based program

-   `jbig2enc <https://github.com/agl/jbig2enc>`__, a library with
    dependencies that is needed for creating PDFs from scans

-   Python 3 version of `py-enchant`

-   `Jupyter` (See Appendix)


Appendix: Juptyer
=================

List written by installing `Jupyter` with Ansible and then running
``/opt/jupyter/bin/pip freeze``:

============================= ====================== ==========================
Requirement                   Name                   Repository
============================= ====================== ==========================
``asn1crypto==0.23.0``        ``py3-asn1crypto``     3.7/main
``python-dateutil==2.6.1``    ``py3-dateutil``       3.7/main
``PyYAML==3.12``              ``py3-yaml``           3.7/main
``requests==2.18.4``          ``py3-requests``       3.7/main
``roman==2.0.0``              ``py3-roman``          3.7/main
``six==1.11.0``               ``py3-six``            3.7/main
``tornado==4.5.2``            ``py3-tornado``        3.7/main
``urllib3==1.22``             ``py3-urllib3``        3.7/main
``bcrypt==3.1.4``             ``py3-bcrypt``         3.7/main
``certifi==2017.7.27.1``      ``py3-certifi``        3.7/main
``cffi==1.10.0``              ``py3-cffi``           3.7/main
``chardet==3.0.4``            ``py3-chardet``        3.7/main
``click==6.7``                ``py3-click``          3.7/main
``cryptography==2.0.3``       ``py3-cryptography``   3.7/main
``docutils==0.13.1``          ``py3-docutils``       3.7/main
``pyasn1==0.4.2``             ``py3-asn1``           3.7/main
``pycparser==2.18``           ``py3-cparser``        3.7/main
``pycrypto==2.6.1``           ``py3-crypto``         3.7/main
``Pygments==2.2.0``           ``py3-pygments``       3.7/main
``PyNaCl==1.2.1``             ``py3-pynacl``         3.7/main
``lxml==4.1.1``               ``py3-lxml``           3.7/main
``MarkupSafe==1.0``           ``py3-markupsafe``     3.7/main
``olefile==0.43``             ``py3-olefile``        3.7/main
``paramiko==2.4.0``           ``py3-paramiko``       3.7/main
``Pillow==4.3.0``             ``py3-pillow``         3.7/main
``Jinja2==2.9.6``             ``py3-jinja2``         3.7/main
``wcwidth==0.1.7``            ``py3-wcwidth``        3.7/community
``pyzmq==16.0.2``             ``py3-zmq``            3.7/community
``decorator==4.1.2``          ``py3-decorator``      3.7/community
``httpie==0.9.9``             ``httpie``             3.7/community
``idna==2.6``                 ``py3-idna``           3.7/community
``pexpect==4.3.1``            ``py3-pexpect``        3.7/community
``jsonschema==2.6.0``         ``py3-jsonschema``     3.7/community
``ptyprocess==0.5.2``         ``py3-ptyprocess``     3.7/community
``jedi==0.11.0``              ``py3-jedi``           edge/testing
``bleach==2.1.2``             None                   None
``entrypoints==0.2.3``        None                   None
``html5lib==1.0.1``           None                   None
``qtconsole==4.3.1``          None                   None
``simplegeneric==0.8.1``      None                   None
``terminado==0.8.1``          None                   None
``testpath==0.3.1``           None                   None
``traitlets==4.3.2``          None                   None
``webencodings==0.5.1``       None                   None
``widgetsnbextension==3.0.8`` None                   None
``jupyter==1.0.0``            None                   None
``jupyter-client==5.1.0``     None                   None
``jupyter-console==5.2.0``    None                   None
``jupyter-core==4.4.0``       None                   None
``mistune==0.8.3``            None                   None
``nbconvert==5.3.1``          None                   None
``nbformat==4.4.0``           None                   None
``notebook==5.2.2``           None                   None
``pandocfilters==1.4.2``      None                   None
``parso==0.1.0``              None                   None
``pickleshare==0.7.4``        None                   None
``prompt-toolkit==1.0.15``    None                   None
``ipykernel==4.7.0``          None                   None
``ipython==6.2.1``            None                   None
``ipython-genutils==0.2.0``   None                   None
``ipywidgets==7.0.5``         None                   None
============================= ====================== ==========================

.. vim: ft=rst
