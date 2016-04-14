:title: Debian APT package management tool
:tags: debian, apt, packages

More apt commands: apt-cache, apt-offline, ppa...

apt-get
=======

* ``apt-get download`` fetches the packages and drops it into the current working directoy.
* ``apt-get install --download-only`` fetches the package and drops it into ``/var/cache/apt/archives/``.


dpkg
====

Omit dependencies or version for dependencies
---------------------------------------------

``--force-depends-version``:

``dpkg -i --force-depends-version libmysqlclient-dev_5.5.47-0ubuntu0.12.04.1_amd64.deb``
