---
layout: post
title:  "PRESTO and TEMPO installation Ubuntu 18.04"
date:   2020-04-02 10:00:00
blurb: "How to install PRESTO and TEMPO on Ubuntu 18.04."
---

This was up to date as of April 2020. It might not be now...
What I've ran on my Ubuntu 18.04 64 bit, with Anaconda Python 3, to install PRESTO and TEMPO:

	sudo apt-get update

	cd ~
	mkdir PULSAR_SOFTWARE

	sudo apt-get install git libfftw3-bin libfftw3-dbg libfftw3-dev libfftw3-doc libfftw3-double3 libfftw3-long3 libfftw3-quad3 libfftw3-single3 pgplot5 csh automake gfortran libglib2.0-dev libccfits-dev libcfitsio5 libcfitsio-dev libx11-dev libpng-dev

	cd PULSAR_SOFTWARE/
	git clone http://git.code.sf.net/p/tempo/tempo

	cd tempo
	./prepare
	./configure
	make && sudo make install
	cp tempo.cfg src/
	cp tempo.hlp src/
	cd ..

	git clone http://github.com/scottransom/presto.git

	sudo gedit /etc/environment

added to the end of my PATH:

	:/home/emma/PULSAR_SOFTWARE/presto/bin"

then added:

	TEMPO="/home/emma/PULSAR_SOFTWARE/tempo/src"

	PRESTO="/home/emma/PULSAR_SOFTWARE/presto"

	PGPLOT_DIR="/usr/lib/pgplot5"

	FFTW_PATH="/usr"


	git clone https://github.com/scottransom/pyslalib.git
	cd pyslalib
	python setup.py install


	cd /home/emma/PULSAR_SOFTWARE/presto/src

	make makewisdom
	make prep
	make
	make clean

	cd $PRESTO ; pip install .

	cd lib
	sudo cp libpresto.so /usr/lib


Note, if you keep PRESTO up to date using GitHub, you will need to run all the lines starting from "make..." to install the updates.
Some Python commands will not work because PRESTO is not entirely compatible with Anaconda installations: https://github.com/scottransom/presto/issues/73 . These ones {pygaussfit.py, prepfold, sum_profiles.py, get_TOAs.py} work.

Sources:

- [https://blog.csdn.net/sinat_34850075/article/details/52434526](https://blog.csdn.net/sinat_34850075/article/details/52434526)

- [https://github.com/scottransom/presto/blob/master/INSTALL](https://github.com/scottransom/presto/blob/master/INSTALL)

- [https://docs.google.com/document/d/1v8Dm4f-SOeDQX5Yli6syek1pxtqgpw81b1cxqoqv2aU](https://docs.google.com/document/d/1v8Dm4f-SOeDQX5Yli6syek1pxtqgpw81b1cxqoqv2aU)

- [http://zhaozhen.me/2017/10/16/ubuntu-software-presto.html](http://zhaozhen.me/2017/10/16/ubuntu-software-presto.html)

- [http://tempo.sourceforge.net/](http://tempo.sourceforge.net/)

- [https://summerpulsar.wordpress.com/2015/01/12/more-presto-installation/](https://summerpulsar.wordpress.com/2015/01/12/more-presto-installation/)

