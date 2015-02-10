Assembling metagenomic data
===============================================

Introduction
------------

This is a tutorial for working with metagonomics assembly.


See the github repo:

https://github.com/voutcn/megahit

And these articles::
#. 

The Tutorial
------------

Installation
------------

This tutorial is setup to run after running Trimmomatic, see `this tutorial <http://khmer-protocols.readthedocs.org/en/v0.8.4/metagenomics/1-quality.html>`_.  After you do read trimming, you'll have 2 sets of files:  se1, se2, pe1, and pe2.  For merging paired end reads, you should use the "quality" trimmed paired read files (pe1 and pe2).

Let's go to the root directory::

	cd /root

If you don't have access, try this::

	sudo bash	
	
To install the latest::

    git clone https://github.com/voutcn/megahit.git

Change directory::

    cd megahit

Build::

    make
    
Download sample file
-------------

Let's go to the working directory::

	cd /mnt
	mkdir Ecoli
	cd Ecoli
	
Download sample file


Merging reads
-------------

Assembling::

    /root/megahit/megahit --cpu-only -m 1e9 -l 250 -r Ecoli/ecoli_ref-5m.fastq.gz -o megahit_5m



And that's it!  



