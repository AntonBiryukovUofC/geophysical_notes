# // geophysical_notes //

My collection of IPython Notebooks. First a few words on how to get Python on your computers.

## FIRST THINGS FIRST: GET PYTHON ON YOUR COMPUTERS

Three options, I have tested personally #1 and #3.

1. *CANOPY

The easiest way is to get Canopy Express, a free download from [Enthought](https://www.enthought.com/products/canopy/), available on all platforms and actively maintained. All the major packages are included as well as many that you will never use; a package manager that takes care of updating all the libraries is also included.

2. *ANACONDA*

A similar solution that I have personally never tried but people swear by it, is [Anaconda](https://store.continuum.io/cshop/anaconda/).

3. *HOMEMADE SOLUTION*

Finally, for those that feel a little bit more adventurous, there is an homemade solution, which has the advantage of being a barebone installation with minimal impact on disk space; full instructions here: <http://penandpants.com/2013/04/04/install-scientific-python-on-mac-os-x/>. It involves installing [Homebrew](http://brew.sh) on your Mac, which is a [package manager](http://en.wikipedia.org/wiki/Package_manager) that is  a must for anybody tinkering with code and unix-like applications.

After having followed the instructions enter this command in a Terminal window get IPyhton running and start coding exactly like you would do in Canopy:

    ipython qtconsole --pylab=inline

This is the way to launch a notebook server to write your own notebooks or load something off the internet like this one:

    ipython notebook

Finally, get [Atom](https://atom.io/) to write your code, preview your markdown etc., and you have a minimal (and free!) scientific system.

### using SEG-Y data

To read and write SEG-Y data in Python you need some library like  [ObsPy](https://github.com/obspy/obspy/wiki) or [Segpy](https://github.com/rob-smallshire/segpy/). Haven't played with Segpy -- which seems a simpler, neater solution though -- so for the moment I will use ObsPy.

ObsPy however is not included in Canopy Express so you have to install it separately. In Windows, open a Canopy command prompt and type in the following commands:

    easy_install lxml
    easy_install sqlalchemy (*)
    easy_install suds>=0.4
    easy_install flake8
    easy_install nose
    easy_install mock
    easy_install obspy

The package `sqlalchemy` complains about a missing compiler which may render things slower, and suggests to install [mingw](http://www.mingw.org/wiki/Getting_Started); that's something for another time.

Under Mac OS X, first install a [fortran compiler](https://gcc.gnu.org/wiki/GFortranBinaries) (also see [this other option](http://coudert.name/software/gfortran-4.8.2-Mavericks.dmg)). Then: `pip install obspy`.

My above mentioned *HOMEMADE SOLUTION* for a working scientific Python system makes this step however much easier, because the required tools (like that fortran compiler) are all taken care of by Brew (the package manager); so you would just type in `pip install obspy` and that's it.


A few links of interest for ObsPy:

* <http://docs.obspy.org/tutorial/>
* gallery with examples: <http://docs.obspy.org/gallery.html>
* tutorial: <http://nbviewer.ipython.org/github/obspy/docs/blob/master/workshops/2014_mess/obspy_introduction.ipynb>

## NOW THE NOTEBOOKS!

### wellmagic

Do magic things with well log data.

* [Creating synthetic data](http://nbviewer.ipython.org/github/aadm/geophysical_notes/blob/master/creating_synthetic_data.ipynb)
* [Creating synthetic data interactive](http://nbviewer.ipython.org/github/aadm/geophysical_notes/blob/master/creating_synthetic_data_interactive.ipynb)

#### support data for wellmagic

* `qsiwell2.csv`: log data from Well 2 of [Quantitative Seismic Interpretation](https://pangea.stanford.edu/researchgroups/srb/resources/books/quantitative-seismic-interpretation)
* `qsiwell2_frm.csv`: qsiwell2 + fluid replaced elastic logs
* `qsiwell2_augmented.csv`: barebones well data, only Ip, Vp/Vs and LFC (litho-fluid class log)
* `qsiwell2_synthetic.csv`: synthetic data generated through Monte Carlo simulation, same logs as in `qsiwell2_augmented.csv` (Ip, Vp/Vs and LFC)

### seismic stuff

How to load and display SEG-Y files, plus some simple ways to play with the data, e.g. extracting amplitude informations, adding noise & filtering.

* [Seismic data in Python](http://nbviewer.ipython.org/github/aadm/geophysical_notes/blob/master/seismic_data_in_python.ipynb)
* [Wedge for AVO]
