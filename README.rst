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
<https://github.com/PromyLOPh/guix-install-action/blob/master/.github/workflows/test.yml>`__
showcases the available options.

Inputs
------

:channels:
    A Scheme expression that describes the Guix channels to use. See `manual
    <https://guix.gnu.org/manual/devel/en/guix.html#Specifying-Additional-Channels>`__


Outputs
-------

:channels:
     The exact channel(s) that were pulled, with commit identifiers.  The output
     can be used as an input for this action to reproduce a previous run.
