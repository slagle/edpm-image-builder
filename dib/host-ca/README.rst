host-ca
=======

host-ca is an element to copy certificate authority files from the host into the
image, then run ``update-ca-trust``.

To use, set DIB_HOST_CA to a list of files on the build host in directory
``/etc/pki/ca-trust/source/anchors/``, for example::

    export DIB_HOST_CA="2015-RH-IT-Root-CA.pem 2022-IT-Root-CA.pem"

Or in a ``diskimage-builder`` command yaml file::

    - imagename: edpm-hardened-uefi
    elements:
    - host-ca
    environment:
        DIB_HOST_CA: "2015-RH-IT-Root-CA.pem 2022-IT-Root-CA.pem"