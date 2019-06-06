.. include:: defined_substitutions.txt

Trimming bad data
=====================

There are two ways of filtering data: trimming ends that may have very
low quality, or removing reads that are low quality. In general,
short-read sequence aligners take quality information into account, and
so conservative trimming and filtering is not necessary. However, if you
have a run with very low quality ends, trimming those ends can help your
analysis, especially if you are assembly a de novo transcriptome.

There are a number of tools designed to help you control read quality,
each with their own benefits. For today, we will use a program called
’Trimmomatic’ because it does a great job of explicitly handling
paired-end data like these. To call Trimmomatic, we will use java, and
simply pass the arguments we want to use. For more detail on each
option, go to the website:
http://www.usadellab.org/cms/?page=trimmomatic.

*One Note:* paired-end data requires two outputs for each file, one for
those that match the opposite direction read, and one for those that
don’t. The code below is an example that may be a helpful starting
point; note that the ‘’ at the end of each line means ‘put this all on
one line; don’t hit return yet’ and can either be copied in directly
(and interpreted by the console), or omitted to put everything on one
line (interpreted by you).


Trimming with ``Trimmomatic``
-------------------------------
  1. Let’s again check our input files to trim:

    .. code:: bash

        cd /home/gea_user/rna-seq-project/data
        ls

  2. These are all single end files, and we can use the following loop to
  process them all

    .. code:: bash

        for infile in /home/gea_user/rna-seq-project/data/*.fq
         do
         base=$(echo ${infile}|cut -f1 -d "."|cut -f6 -d "/")
         trimmomatic\
          SE -phred64 ${infile} ${base}_trimmed.fq\
          CROP:85 HEADCROP:4\
          LEADING:3 TRAILING:3\
          SLIDINGWINDOW:4:15 MINLEN:30
         done

  3. We should now have 16 trimmed fastq files

    .. code:: bash

        ls *_trimmed.fq

  4. let’s move these to a directory

    .. code:: bash

        mkdir /home/gea_user/rna-seq-project/trimmed-reads
        mv *_trimmed.fq /home/gea_user/rna-seq-project/trimmed-reads

  5. Let’s run another round of fastqc on the trimmed results to compare

    .. code:: bash

        cd /home/gea_user/rna-seq-project/trimmed-reads
        fastqc *.fq

  6. Let’s move these results to their own space

    .. code:: bash

        mkdir -p /home/gea_user/rna-seq-project/trimmed-reads/fastqc-results
        mv *.html /home/gea_user/rna-seq-project/trimmed-reads/fastqc-results
        mv *.zip /home/gea_user/rna-seq-project/trimmed-reads/fastqc-results

You can browse your HTML (website) results in the filebrowser on the
left (rna-seq-project > trimmed-reads> fastqc-results).

.. admonition:: Question
   :class: admonition-question

   Why use `FastQC` after using `Trimmomatic`?

   .. admonition:: Answer

      While not required, you may wish to run `fastqc` again to
      verify trimming has improved the quality of the sample data.



----

.. Comment: Place Images Below This Line
   use :width: to give a desired width for your image
   use :height: to give a desired height for your image
   replace the image name/location and URL if hyperlinked

 .. |Static image| image:: ./img/IMAGENAME.png
    :width: 25
    :height: 25

 .. |Clickable hyperlinked image| image:: ./img/IMAGENAME.png
    :width: 500
    :height: 100
 .. _link : http://link-url

.. Comment: Place URLS Below This Line

   # Use this example to ensure that links open in new tabs, avoiding
   # forcing users to leave the document, and making it easy to update links
   # In a single place in this document

   .. |Substitution| raw:: html # Place this anywhere in the text you want a hyperlink

      <a href="REPLACE_THIS_WITH_URL" target="blank">Replace_with_text</a>


.. |Github Repo Link|  raw:: html

   <a href="FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX" target="blank">Github Repo Link</a>
