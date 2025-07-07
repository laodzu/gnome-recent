gnome-recent: Accessing GNOMEs list of recently used URIs from the shell
========================================================================

Usage
-----

Working in a shell it is sometimes desirable to seemlessly work with
files accessed just before in other parts of the GNOME environment. Of
course filename completion already saves us a lot of keystrokes in the
shell but sometimes I find it difficult to remember the directory part
of the first few characters of such a recently used file.  This
pathetic little script helps me out in these cases.

In the following example I just downloaded a cross compilation
toolchain for the Zephyr OS with Firefox and for installation I need
to make it executable and run it.  Without the need to remember the
download directory or the filename itself, this is then easy to do:

.. code-block:: console

  dzu@krikkit:~$ gnome-recent 
  /home/dzu/Downloads/zephyr-toolchain-arm-0.12.2-x86_64-linux-setup.run
  dzu@krikkit:~$ chmod a+x `gnome-recent`
  dzu@krikkit:~$ sudo `gnome-recent`
  [sudo] Passwort für dzu: 
  Verifying archive integrity...  100%   All good.
  Uncompressing arm toolchain for Zephyr  100%  
  Enter target directory for SDK (default: /root/zephyr-sdk/): 

Requirements
------------

The shell scripts requires `jq <https://stedolan.github.io/jq/>`_ and
the ``xq-python`` tool bundled with `yq
<https://github.com/kislyuk/yq>`_.

While ``jq`` and ``yq`` should be available in distibutions, ``yq``
can be installed via the Python package manager ``pip`` if neccessary.
In a Debian based environment these two commands should usually do the
trick::

  sudo apt install jq
  pip3 install yq
