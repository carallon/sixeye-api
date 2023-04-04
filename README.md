# SixEye API Documentation

This is the repository for the public SixEye API documentation. The documentation is written using Sphinx, and this generates HTML documentation for publication.

## Prerequisites

You need to have [Sphinx](http://www.sphinx-doc.org/en/stable/) installed to build this documentation.

You can install Sphinx and other python dependencies from the requirements file. From the root directory of the project you can run:

    pip install -r sphinx-src/requirements.txt

where `pip` might need to be `pip3` or similar if you've installed pip under another name.

The project Makefile assumes your python executable is `python`. If it's anything other than `python` then you should define the `SPHINXBUILD` environment variable to be `{your python executable} -msphinx`, e.g. `python3 -msphinx`.

## Build instructions

From the root directory of the project you can run, on Linux or macOS:

    make html

or on Windows:

    .\make.bat html

This will create the html output in the `build` directory (which will be created if building for the first time).
