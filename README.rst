.. image:: https://img.shields.io/badge/dmtn--165-lsst.io-brightgreen.svg
   :target: https://dmtn-165.lsst.io
.. image:: https://github.com/lsst-dm/dmtn-165/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/dmtn-165/actions/

#################################################
A Hybrid Notification and Alert Retrieval Service
#################################################

DMTN-165
========

We consider the implications of providing a subset of alert packet contents in the alert stream, with the full alert packets available for rate-limited retrieval using an identifier included in the "lightweight" alert.
This hybrid approach would enable much wider dissemination of the complete lightweight alert stream, potentially to thousands more users than is possible in the current baseline.
In turn this "alerts on your laptop" access would allow users to conduct more sophisticated filtering and analysis than the current Alert Filtering Service, increasing the overall scientific returns of the alert stream.
Community brokers would still be able to retrieve all of the contents of the full alert stream within the 60 second latency window and would gain greater control over their ingestion of the bulk alert data.
Technically, this hybrid system may represent a modest increase in complexity over the current baseline but is likely to be more operationally robust.

Links
=====

- Live drafts: https://dmtn-165.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-165

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-165

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
