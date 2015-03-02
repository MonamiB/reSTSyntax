
reStructuredText Syntax
=======================

This document outlines the documentation template and reStructuredText (reST) directives for composing a simple source file for API documentation. The general structure, irrespective of its output format, is:

* Page. 1:
    - Document title
    - Subtitle (version)
    - Date created or revised
* Page. 2 - Blank
* Page. 3
    - Table of contents
* Page. 4 - Blank
* Page. 5 onward:
    - Chapter - Heading level 1
    - Section - Heading level 2
        + Sub-subsection - Heading level 3
            * Sub-sub-subsection - Heading level 4

Document Structure
------------------

For the document title, subtitle, chapter name, heading, and sub-headings, you can use the following syntax. ::

    =======
     Title
    =======

    -------------------
     Optional Subtitle
    -------------------

    :Author: Author Name
    :Date Created DD MONTH, YY
        
    Chapter 1
    =========

        Section 1.1
        -----------

            Subsection 1.1.1
            ~~~~~~~~~~~~~~~~
        
            Subsection 1.1.2
            ~~~~~~~~~~~~~~~~
                Sub-subsection 1.2.2.1
                ``````````````````````

        Section 1.2 Title
        -----------------

    Chapter 2
    =========

It is important to adhere to the same sequence when using various special characters for format identification.

Standard Inline Markups
-----------------------

You can use standard symbols and special characters as inline markups as described in the following table.

==============  ==================  =============
    Style             Symbol            Result
==============  ==================  =============
Bold               `**bold**`       **bold**
Italics            `*italics*`      *italics*
Bold & Italics  Not a feature. Can       N.A.
                be encoded.*                  
Inline code      \``backticks``\    ``backticks``
Escape markup   backslash (``\``)   You can see 
                before symbol (\*)  the asterisk
                                    \*                
==============  ==================  =============

`*` To learn how to define roles for styles and markups, see the Sphinx documentation for `strikethrough <http://stackoverflow.com/questions/6518788/rest-strikethrough>`_ and stackoverflow forum for `bold-italics <http://stackoverflow.com/questions/11984652/bold-italic-in-restructuredtext>`_.

List Syntax
-----------
You can use special characters, numerals, and manual tabs to create bulleted ajd numbered lists.

Bulleted List
~~~~~~~~~~~~~
To create a bulleted list, use a single special character followed by a space before any text.
For nested sub-levels, use tabs and a distinct special character to identify it.
It is advised to use the same symbols consistently to avoid confusion.

**Sample** ::

    This is the raw text.
    * Bullet level 1 of 3
        - Sublevel 1.1
            + Sub-sublevel 1.1.1
            + Sub-sublevel 1.1.2
    * Bullet level 2 of 3
    * Bullet level 3 of 3
        - Sublevel 3.1
            + Sub-sublevel 3.1.1
                * Sub-sub-sublevel 3.1.1.1
                * Sub-sub-sublevel 3.1.1.2
            + Sub-sublevel 3.1.2
        - Sublevel 3.2    
            

This is how it will render in the output.

* Bullet level 1 of 3
    - Sublevel 1.1
        + Sub-sublevel 1.1.1
        + Sub-sublevel 1.1.2
* Bullet level 2 of 3
* Bullet level 3 of 3
    - Sublevel 3.1
        + Sub-sublevel 3.1.1
            * Sub-sub-sublevel 3.1.1.1
            * Sub-sub-sublevel 3.1.1.2
        + Sub-sublevel 3.1.2
    - Sublevel 3.2

Numbered List
~~~~~~~~~~~~~
To document procedures and step-by-step instructions you can use numbers, roman numerals, upper or lowercase alphabets. The following directives are accepted: ::

    1. Step identifier followed by a period and space.
    2) Step identifier followed by a parenthesis and space.
    (3) Step identifier enclosed in parentheses followed by a space.
    
**Sample:** ::

    This is the raw text.
    1. Step 1 of 3.
        i) Substep 1.1
        ii) Substep 1.2
            a. Sub-substep 1.2.1
            b. Sub-substep 1.2.2
    2. Step 2 of 3.
        i) Substep 2.1
            a. Sub-substep 2.1.1
            b. Sub-substep 2.1.2
        ii) Sub-substep 2.2
    3. Step 3 of 3
        i) Substep 3.1
            a. Sub-substep 3.1.1
            b. Sub-substep 3.1.2
        ii) Sub-substep 3.2
        iii) Sub-substep 3.3
            a. Sub-substep 3.3.1
            b. Sub-substep 3.3.3
            c. Sub-substep 3.3.3

This is how it will render in the output.

1. Step 1 of 3.

    i) Substep 1.1.
    ii) Substep 1.2.
    
        a. Sub-substep 1.2.1.
        b. Sub-substep 1.2.2.
2. Step 2 of 3.
    i) Substep 2.1.
        a. Sub-substep 2.1.1.
        b. Sub-substep 2.1.2.
    ii) Sub-substep 2.2.
3. Step 3 of 3.
    i) Substep 3.1.
        a. Sub-substep 3.1.1.
        b. Sub-substep 3.1.2.    
    ii) Sub-substep 3.2.
    iii) Sub-substep 3.3.
        a. Sub-substep 3.3.1.
        b. Sub-substep 3.3.2.
        c. Sub-substep 3.3.3.

Tables
------

Simple Table
~~~~~~~~~~~~

For fewer items, you may also use a simple table as shown below. ::

    ==============  ==================  =============
    Parameter Name  Mandatory/Optional  Default Value
    ==============  ==================  =============
    False           False               False
    True            False               False
    False           True                False
    True            True                True
    ==============  ==================  =============
    
This table will appear as follows:

==============  ==================  =============
Parameter Name  Mandatory/Optional  Default Value
==============  ==================  =============
False           False               False
True            False               False
False           True                False
True            True                True
==============  ==================  =============

Multiple Heading Table
~~~~~~~~~~~~~~~~~~~~~~
You can modify a simple table to have a multiple, split-level heading as shown below. ::

    ==========  ==============  ============
      Level 1, Column 1         Level 1,
                                Column 2
    --------------------------  ------------
    Level 2, 1    Level 2, 2     Level 2, 3
    ==========  ==============  ============
    False       False           False
    True        False           True
    False       True            True
    True        True            True
    ==========  ==============  ============
    
The above table will appear as follows:

==========  ==============  ============
  Level 1, Column 1         Level 1,
                            Column 2
--------------------------  ------------
Level 2, 1    Level 2, 2     Level 2, 3
==========  ==============  ============
False       False           False
True        False           True
False       True            True
True        True            True
==========  ==============  ============

Grid Table
~~~~~~~~~~
A grid table can be created as shown below: ::

    +----------------+--------------------+---------------------+
    |  Title         | Description        |     Syntax          |                            
    +================+====================+=====================+
    |When you need to|                    |                     |
    |write multiple  |                    |                     |
    |lines in the    |                    |                     |
    |same cell       |                    |                     |
    |                |                    |                     |                            
    |                |                    |                     |                            
    |                |                    |                     |                            
    |                |                    |                     |                            
    |                |                    |                     |                             
    +----------------+--------------------+---------------------+
    |Merge           |This is an example of merged columns      |
    |                |                                          | 
    +----------------+--------------------+---------------------+
    |Merge (contd.)  |This is an example  |                     |                            
    |                |of merged rows      |                     |
    +----------------+                    +---------------------+
    |                |                    |                     |
    |                |                    |                     |                                                        
    |                |                    |                     |
    +----------------+--------------------+---------------------+
    |Symbols and     |This is an example of multiple rows and   |
    |special         |columns merged                            |
    |characters      |                                          |                      
    +----------------+                                          +
    |                |                                          |                            
    +----------------+--------------------+---------------------+
    
This table will appear as below in an HTML output:

+----------------+--------------------+---------------------+
|  Title         | Description        |     Syntax          |                            
+================+====================+=====================+
|When you need to|                    |                     |
|write multiple  |                    |                     |
|lines in the    |                    |                     |
|same cell       |                    |                     |
|                |                    |                     |                            
|                |                    |                     |                            
|                |                    |                     |                            
|                |                    |                     |                            
|                |                    |                     |                             
+----------------+--------------------+---------------------+
|Merge           |This is an example of merged columns      |
|                |                                          | 
+----------------+--------------------+---------------------+
|Merge (contd.)  |This is an example  |                     |                            
|                |of merged rows      |                     |
+----------------+                    +---------------------+
|                |                    |                     |
|                |                    |                     |                                                        
|                |                    |                     |
+----------------+--------------------+---------------------+
|Symbols and     |This is an example of multiple rows and   |
|special         |columns merged                            |
|characters      |                                          |                      
+----------------+                                          +
|                |                                          |                            
+----------------+--------------------+---------------------+

Code Syntax
-----------
You can format inline code as well as a pre-formatted code block.

Code Block
----------
For a pre-formatted code block, place a double-colon "::" at the end of the sentence preceeding the code-block.

Highlighted Code Block
----------------------
To highlight the code sample, use the ".. code::" directive.
Ensure that the code snippet is indented using 4 spaces. The code block directive ends as soon as a sentence, following the code sample, returns to the original indentation.

**Sample:**

.. code::

    .. code::
    
    This sentence is preceeded by 4 spaces for indentation. 

Inline Code
-----------
For inline code syntax, see :ref:`std-markup-label`

Image Reference
===============
To display an image by reference, use the "image" directive. ::

    .. image:: images/image.png
    
To place attribute restrictions, use the following format: ::

    .. image:: images/image.png
     :height: 100
     :width: 200
     :scale: 50
     :alt: alternate text
     

Hyperlinking and Cross-reference
================================ 

Hyperlink
---------

This is how you hyperlink. ::

    `Link text <http://example.com/>`_

**Sample**

Typing "\`Hyperlinking to my site is easy! <http://projectemm.com/>`_" results in `Hyperlinking to my site is easy! <http://projectemm.com/>`_

Cross-reference
---------------

reST allows you to link to:

* A section (heading) within the document
* A section (heading) in another document
* Another document (HTML only)
* An image
* A downloadable file


Cross-reference Within Document
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Cross-reference Another Document
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Cross-reference a Heading in Another Document
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Cross-reference An Image
~~~~~~~~~~~~~~~~~~~~~~~~


File Download Link
~~~~~~~~~~~~~~~~~~


Footnotes
---------
You can add multiple footnotes using the hashtag in the reference label as demonstrated here: ::

    .. [#] Sample footnote 1
    .. [#] Sample footnote 2
    .. [#] Sample footnote 3

The above syntax will render as follows:

.. [#] Sample footnote 1
.. [#] Sample footnote 2
.. [#] Sample footnote 3
    



