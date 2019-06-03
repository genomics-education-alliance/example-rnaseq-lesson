.. include:: defined_substitutions.txt

Background
================================

After sending off your RNA for sequencing (or downloading it from SRA) and
waiting patiently, you finally have data! . . . Now what? The files you have
received contain billions of bases of sequence with information on quality, but
where to begin? This module is the first step in that processing, and the first
time we will be working directly at the command line interface with our data.
Next generation sequencing platforms, by virtue of their large outputs, are
bound to produce some errors. The goal of this module is to identify and remove
many of these errors.

Checking data quality
=======================

  .. admonition:: learning-objectives

     - Learn about sequencing quality scores
     - Learn how to identify potential problems in sequencing data
     - Learn how to handle and remove these potential errors
     - Understand the indicators of quality sequence data
     - Manage a large dataset without terror

Checking data quality
-----------------------

The first step of the process of data filtering is simply to see what you have.
The data are provided to us in a format called “fastq” that includes a quality
score, which provides information on how confident the sequencer is in its base
calls. We will talk about this more in class, but the basic idea is that for
Illumina runs, the score (Q) is calculated as:

.. math::

   Q = -10 * \log_{10}P

Where ‘P’ is the probability that the base call is incorrect. Thus, a larger Q
score indicates greater confidence in the base call. These scores are encoded
along with the sequence information using the ASCII values corresponding to
various characters with some offset to avoid the nonprinting characters at the
low end of ASCII values. As a general rule, scores over 20 suggest high quality
data, while lower scores may be a cause for some concern. The steps below will
walk us through how to identify those scores in a useful way. This, like most of
the linux command line steps, will occur on the CyVerse Discovery Environment.


Running FastQC
-------------------
You will each be assigned to a sequence file(s), which will be yours to take all
the way through this analysis. Each of you will execute the following,
substituting your assigned file for files.

**CyVerse Login and App Launch**

  1. Step one log in to the CyVerse Discovery Environment.
  2. Go to apps and find GEA app
  3. Do something in the app and click launch
  4. Launch the app


**Running the App**

  1. Click the notebook in Jupyterlab
  2. Let's copy the data into a project folder in our home folder. First we will
     make the project folder:

    .. code:: bash

       mkdir ~/rna-seq-project

  3. Then we will copy our RNA-Seq reads into this folder

    .. code:: bash

       cp -r /gcatseek-data ~/rna-seq-project

  4. Now let's check the content of our ~/rna-seq-project folder

    .. code:: bash

       ls -R rna-seq-project

  As you can see, we have 16 fastq files to analyze. To get the data, we will
  use a program called ``fastqc``. To run the program we use the command ``fastqc``
  and the name of the file we wish to analyze.

  5. We will move into the directory where are data are stored.

    .. code:: bash

       cd ~/rna-seq-project/gcatseek-data

  6. We will analyze one file to get familiar with the ``fastqc`` output:

    .. code:: bash

       fastqc female_A.fq

  7. Our output is returned in two files:

     - A ``.html`` file (than can be viewed as a webpage)
     - A ``.zip`` file that contains individual images and reports

     Let's look at these files:

    .. code:: bash

       ls *.html && ls *.zip

  8. We will run ``fastqc`` on all our files and examine the output in the next
     notebook:

    .. code:: bash

       fastqc *.fq

  9. Let's create a results folder and move all results there:

    .. code:: bash

       mkdir -p fastqc-results
       mv *.zip fastqc-results
       mv *.html fastqc-results

You can browse your HTML (website) results in the filebrowser on the left
(rna-seq-project > gcatseek-data > fastqc-results).


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
