# Calculate absorption table and nadir OLR spectrum

2020-09-30 Stefan Buehler

Prerequisites: pyarts (for calculation), typhon (here just used in plotting). 

If you do not want the sourcecode yourself, you can simply install them with

    pip install pyarts
    pip install typhon

If you do want the sourcecode, you can get it for both packages from the [atmtools project on github](https://github.com/atmtools). Github also has the [documentation for the pyarts API](https://atmtools.github.io/pyarts-docs-master/). 
    
To check out the line catalog and atmosphere data, you will need subversion installed (which should anyway be available on most systems). Also, you should have around 4 GB of RAM, the main memory hog is that we read in a large part of the HITRAN catalog.

The absorption lookup table format is described in [this paper](https://doi.org/10.1016/j.jqsrt.2011.03.008).

You can see documentation for all ARTS variables and methods in the online browser for the [built-in documentation](https://www.radiativetransfer.org/docserver-trunk). 

On the [ARTS webpage](https://www.radiativetransfer.org) there are also pointers to more traditional documentation (User guide, Theory guide, Developer guide). Not all of these are completely up to date, especially the python interface so far is poorly documented.

This demo takes 1.5 minutes to run on my mac mini, whereof 1 minute is just the reading of the spectral line catalog files, and the rest is mostly the absorption table calculation. (We should probably think about adding a binary format option for the line catalogs, which would make a big difference to the reading speed.) 

The absorption calculation itself is quite complete in terms of species and spectral line coverage. The only adjustment introduced to make the demo small is that it uses only 250 frequencies (so a very coarse frequency spacing of 10 Kayser). This can be easily changed below where the frequency grid is set.

This example itself is also [in my own repository on github](https://github.com/stefanbuehler/jupyter_arts_olr_spectrum).

<!--
You can directly run this in the cloud with binder by clicking on the button below:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/stefanbuehler/jupyter_arts_olr_spectrum/master?filepath=arts_spectrum.ipynb)

However, the job will not run through, because binder gives you only at max. 2GB of RAM which is 
insufficient. 
-->
