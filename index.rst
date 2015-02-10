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

Here is another great resource. 'this tutorial <https://github.com/ctb/2014-megahit-evaluation>'

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
	
Download sample file::

	curl -O https://s3.amazonaws.com/public.ged.msu.edu/ecoli_ref-5m.fastq.gz


Assemby reads
-------------

Assembling::

    /root/megahit/megahit --cpu-only -m 1e9 -l 250 -r Ecoli/ecoli_ref-5m.fastq.gz -o megahit_5m



Evaluating assembly
-------------
Get E coli reference genome::

	curl -O https://s3.amazonaws.com/public.ged.msu.edu/ecoliMG1655.fa.gz
	gunzip ecoliMG1655.fa.gz
	
Install quast::
	cd /root
	curl -O -L https://downloads.sourceforge.net/project/quast/quast-2.3.tar.gz
	tar xzf quast-2.3.tar.gz
	
Run quast::
	cd /mnt/Ecoli
	/root/quast-2.3/quast.py -R Ecoli/ecoliMG1655.fa megahit_5m/final.contigs.fa -o quast_5m


And that's it!  



