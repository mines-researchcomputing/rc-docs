# CIARC-docs-sphinx

This repository stores the build process for the webpages at https://wpfiles.mines.edu/ciarc/docs. They are generated using the [Sphinx](https://www.sphinx-doc.org/en/master/) Python documentation generator, accomplained by the [Read The Docs](https://readthedocsorg.readthedocs.io/en/latest/theme.html) theme. 

## Requirements

This requires a copy of Sphinx on your local machine. We recommend using [Anaconda](https://anaconda.org) to setup an environment for building Sphinx pages. 

## Setting up Sphinx environment with Anaconda
1. Download and install anaconda following these instructions: [Linux](https://docs.anaconda.com/anaconda/install/linux/), [macOS](https://docs.anaconda.com/anaconda/install/mac-os/), [Windows](https://docs.anaconda.com/anaconda/install/windows/)
2. Open the conda command prompt (Windows) or reload your terminal (Linux, MacOS) with [conda in your PATH](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html#regular-installation) and create a new conda environment for sphinx:

	conda create -n sphinx_env

and confirm by typing "y" and pressing enter.

3. Activate the conda environment:
	conda activate sphinx_env

4. Install Sphinx:
	conda install sphinx
and confirm by typing "y" and pressing enter.

5. Install plugins for markdown and the Read the Docs theme:
	pip install sphinx_rtd_theme sphinx_rtd_theme myst_parser nbsphinx ipython

Now whenever you want to update sphinx pages, repeat step 3 only, assuming conda is your environment path.

## Building pages
In order to build pages, first change directories to the `./source` folder:

	cd ./source

you can now build the html pages by issuing the command

	make html

The generated pages will now appear under `./build/html`. Open `./build/html/index.html` to view the front page of the Sphinx docs that have been generated.

## Making a new page

Currently, all new pages will be added under `./source/pages` as `.md` files. Once you add your new page, call it `test.md`, you will need to update the `./source/index.rst` file to include the new page. Adding the new entry to `index.rst` will look like:

      .. test documentation master file, created by
         sphinx-quickstart on Mon Jan 24 13:53:10 2022.
         You can adapt this file completely to your liking, but it should at least
         contain the root `toctree` directive.

      Welcome to HPC at Mines documentation!
      =========================================

      .. toctree::
         :maxdepth: 3
         :caption: Contents:

         pages/overview.md
         pages/systems_policies.md
         pages/new_user_guide.md
         pages/test.md

      Indices and tables
      ==================

      * :ref:`genindex`
      * :ref:`modindex`
      * :ref:`search`  

## To Do

1. Setup Gitlab CI/CD to push html files to server using sftp
2. Decide Table of Contents and how to organize documentation

 
