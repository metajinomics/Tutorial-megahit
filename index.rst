Assembling metagenomic data
===============================================

Introduction
------------

This is a tutorial for working with metagonomics assembly.


See the github repo:

https://github.com/voutcn/megahit

And these articles::
#. Li, D., Liu, C. M., Luo, R., Sadakane, K., & Lam, T. W. (2015). MEGAHIT: An ultra-fast single-node solution for large and complex metagenomics assembly via succinct de Bruijn graph. Bioinformatics, btv033. doi:10.1093/bioinformatics/btv033

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

    /root/megahit/megahit --cpu-only -m 1e9 -l 250 -r ecoli_ref-5m.fastq.gz -o megahit_5m







And that's it!  


