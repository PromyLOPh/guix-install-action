Install GNU Guix (GitHub Action)
================================

.. image:: https://github.com/PromyLOPh/guix-install-action/workflows/test/badge.svg

This GitHub action installs GNU Guix, a functional package manager and
distribution, inside a GitHub Action runner.

It can be used to build Guix packages themselves, but also to create
deliverables like self-contained relocatable binaries, Docker images or
SquashFS filesystems. See `guix pack
<https://guix.gnu.org/manual/devel/en/guix.html#Invoking-guix-pack>`__ for more
information.

`This repository’s test action
<https://github.com/PromyLOPh/guix-install-action/blob/v1/.github/workflows/test.yml>`__
showcases the available options.

Inputs
------

:channels:
    A Scheme expression that describes the Guix channels to use. See `manual
    <https://guix.gnu.org/manual/devel/en/guix.html#Specifying-Additional-Channels>`__
:guixBinaryUrl:
    Use custom location for downloading the Guix binaries. This can be
    used in combination with ``pullAfterInstall: false`` to fetch a more
    recent tarball built with

    .. code:: bash

        guix pack -C xz --fallback --localstatedir --profile-name=current-guix -e '((@ (gnu packages package-management) current-guix))'
:pullAfterInstall:
    Run `guix pull` after installing Guix. If set to `false` the latest
    Guix package as defined in `(gnu packages package-management)`
    will be used, which is older than the git master.

Outputs
-------

:channels:
     The exact channel(s) that were pulled, with commit identifiers.  The output
     can be used as an input for this action to reproduce a previous run.
