.. include:: defined_substitutions.txt

RNA-Seq: Sequence processing and quality control
===================================================

**Authors:** Mark P Peterson, Juniata College Jacob T Malloy, Juniata College Vincent P Buonaccorsi, Juniata College James H Marden, Viterbo University

**Corresponding author and contact info:** williams@cshl.edu

Prerequisites and Lesson Categories
-----------------------------------

Lesson Abstract
~~~~~~~~~~~~~~~
Next-generation sequencing is radically changing the study of biology, but there are currently few resources aimed at teaching the required laboratory and data-analysis skills to undergraduate students. This gap is especially true at primarily undergraduate institutions, where even the faculty are likely to encounter barriers related to funding, equipment, and training needed to begin research or teaching of sequencing and the associated bioinformatics. For this reason, the GCAT-SEEK network has been developed to provide training, data, and teaching materials specifically geared for general biology undergraduates and their instructors. This lesson plan was created to teach RNA-Seq analysis as a part of that effort. It is provided here, both in finished form and with the modifiable source code, to allow flexible adaptation to various classroom settings. In addition, we include a relevant tutorial to ease students and faculty into the R statistical environment. The associated materials are directly applicable to both faculty training and classroom settings. We expect implementation of the tutorial to strengthen bioinformatic knowledge and skills for general biology students.

- **Keywords**: RNA-Seq, GCAT-SEEK, R, UNIX

- **Approximate instructional time (min)**: 90

Student Prerequisites
~~~~~~~~~~~~~~~~~~~~~~

-  **Recommended prior course work:** Advanced biology electives (genetics, bioinformatics, molecular biology, biochemistry, etc.)

-  **Recommended computer skills:** Intermediate: Basic skills listed above + familiarity with Excel

Instructor Prerequisites
~~~~~~~~~~~~~~~~~~~~~~~~~

- **Implementation requirements:** Basic Computer Lab (Access to laptops/desktops, no large memory or cpu requirements)

- **Individual and/or team student work:** Either individual or team work is possible

- **Additional lesson resources included:** Sample data sets

Lesson Topic Tags
~~~~~~~~~~~~~~~~~~

-  **Science:** Molecular biology, Genetics

-  **Math/statistics:** Distributions

-  **Bioinformatics:** Data cleaning, Coding/scripting


Competencies and Other Classifications
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**NIBLSE Bioinformatics**

- C1. Explain the role of computation and data mining in addressing hypothesis-driven and hypothesis-generating questions within the life sciences
- C3. Apply statistical concepts used in bioinformatics
- C4. Use bioinformatics tools to examine complex biological problems in evolution, information flow, and other important areas of biology
- C7. Use command-line bioinformatics tools and write simple computer scripts


Lesson table of contents
--------------------------

.. toctree::
	:maxdepth: 1

	Lesson cover page <self>
	Checking data quality <section-1.rst>
	Trimming bad data <section-2.rst>
	Lesson summary <section-summary.rst>
	Glossary <section-glossary.rst>

	Delete this example guide page <example_directives_delete.rst>
..

----

.. Comment: Place Images Below This Line
   use :width: to give a desired width for your image
   use :height: to give a desired height for your image
   replace the image name/location and URL if hyperlinked

 .. |Clickable hyperlinked image| image:: ./img/IMAGENAME.png
    :width: 500
    :height: 100
 .. _link : http://link-url

 .. |Static image| image:: ./img/IMAGENAME.png
    :width: 25
    :height: 25



.. Comment: Place URLS Below This Line

   # Use this example to ensure that links open in new tabs, avoiding
   # forcing users to leave the document, and making it easy to update links
   # In a single place in this document

   .. |Substitution| raw:: html # Place this anywhere in the text you want a hyperlink

      <a href="REPLACE_THIS_WITH_URL" target="blank">Replace_with_text</a>


.. |Github Repo Link|  raw:: html

   <a href="FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX_FIX" target="blank">Github Repo Link</a>
