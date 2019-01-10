VOLTHA in iOrchard
===================

This is a forked one from opencord/voltha.

We did a project - Developing CORD-based cloud network platform - in 2018.

We are trying to support Dasan Networks ONU to work with voltha.

How to build an image
----------------------

Go to voltha/ and build a container image.::

    $ cd voltha
    $ VOLTHA_BUILD=docker make build

There will be an image named 'voltha-voltha'.::

    $ docker images |grep voltha-voltha
    ...
    voltha-voltha   latest b8db866fc7e7        4 weeks ago         789MB

How to test a newly built image
--------------------------------

You can make a tarball of image.::

    $ docker save voltha-voltha | gzip > voltha-voltha.tar.gz

Send a tarball to voltha machine and load it.::

    $ scp voltha-voltha.tar.gz <voltha-machine>:~/
    voltha-machine$ zcat voltha-voltha.tar.gz | docker load

Now, you can use voltha image in voltha-machine to create a voltha container.
