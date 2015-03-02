
reStructuredText Syntax
=======================

This document outlines the reStructuredText (reST) directives commonly used to write the source content for API documentation.

Titles and Headings
===================

For the document title, subtitle, and additional information in the cover page, use the following syntax. ::

    =======
     Title
    =======

    -------------------
     Optional Subtitle
    -------------------

    :Author: Author Name
    :Date Created DD MONTH, YY
    
For the chapter names, headings, and sub-headings, you can use the following syntax. ::
    
    =========    
    Chapter 1
    =========

    Section 1.1
    ===========

    Subsection 1.1.1
    ----------------
        
    Subsection 1.1.2
    ----------------
    
    Sub-subsection 1.2.2.1
    ~~~~~~~~~~~~~~~~~~~~~~
    
    Sub-sub-subsection 1.2.2.1.1
    ````````````````````````````

    Section 1.2 Title
    =================

    =========
    Chapter 2
    =========

*Note: It is important to maintain consistent usage of the symbols/special characters and their sequence.*

Standard Inline Markups
=======================

You can use standard symbols and special characters as inline markups.

==============  ==================  =============
    Style             Symbol            Result
==============  ==================  =============
Bold               `**bold**`       **bold**
Italics            `*italics*`      *italics*
Bold & Italics  Not a feature. Can       N.A.
                be encoded.                  
Inline code      \``backticks``\    ``backticks``
Escape markup   backslash (``\``)   You can see 
                before symbol (\*)  the asterisk
                                    \*           
==============  ==================  =============

List Syntax
===========
You can use special characters, numerals, and manual tabs to create bulleted amd numbered lists.

Bulleted List
-------------
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
-------------
To document procedures you can use numbers, roman numerals, and upper or lowercase alphabets. The following directives are accepted: ::

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
======

Simple Table
------------

For fewer items with short descriptions you can use a simple table format. ::

  This is the raw text for a simple table format.
  
    ==============  ==================  =============
    Parameter Name  Mandatory/Optional  Default Value
    ==============  ==================  =============
    False           False               False
    True            False               False
    False           True                False
    True            True                True
    ==============  ==================  =============

This table will render as follows:

==============  ==================  =============
Parameter Name  Mandatory/Optional  Default Value
==============  ==================  =============
False           False               False
True            False               False
False           True                False
True            True                True
==============  ==================  =============

Split Heading Table
-------------------

You can modify a simple table to have a multiple, split-level headings as shown below. ::

  This is the raw text for a split heading table:
  
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

The above table will render as follows:

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
----------

For complex representations, you can use a grid table. ::
  
  This is the raw text for a complex grid table.
  
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

This his how the table will render in an HTML output:

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

Code
====

You can format code inline, as a pre-formatted code block or a sidebar container (see the :ref:`sidebar_label`).

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
You can use reST labels for cross-referencing. ::

    If a label as shown in the sample label, preceeds the section:
    .. _sample_label:
    
    Section Heading
    ---------------
    
    You can cross-reference the section as:
    :ref:`sample_label`
    
Note: The blank line between the label and the subsequent section heading is necessary. The \:ref: directive will automatically render the section title.


Cross-reference a Document
~~~~~~~~~~~~~~~~~~~~~~~~~~
You can reference a document with an absolute path or a relative path. ::
   
    :doc: 

This will render in the output as: ::


Cross-reference a Section in another Document
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Image Cross-reference
~~~~~~~~~~~~~~~~~~~~~


External File Download Link
~~~~~~~~~~~~~~~~~~~~~~~~~~~


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
    
Defining Roles
--------------
To learn how to define roles for new styles and markups, see the following documentation:

* `strikethrough <http://stackoverflow.com/questions/6518788/rest-strikethrough>`_
* `bold-italics <http://stackoverflow.com/questions/11984652/bold-italic-in-restructuredtext>`_
* `reference <http://sphinx-doc.org/markup/inline.html>`_

.. _sidebar_label:

Sidebar Container
-----------------
Use the sidebar directive for the container. The boundary should be indented (recommended to avoid using Tab. Use 4 spaces) content in the boundary. ::

    .. sidebar:: This  is a sidebar container sample

    ================== =============
    ``Asterisk \*``    Asterisk \*
    ``back-quote \```  back-quote \`
    ``**mark**\ up.``  **mark**\ up.
    ================== =============
    
This is how it will appear in the output:

.. sidebar:: This  is a sidebar container sample

    ================== =============
    ``Asterisk \*``    Asterisk \*
    ``back-quote \```  back-quote \`
    ``**mark**\ up.``  **mark**\ up.
    ================== =============

For a code sample, you can use the sidebar directive as follows: ::

    .. sidebar:: Sample code representation

       ::

          code sample line 1
          wrapped line 2
          wrapped line 3
          
          new line 2   

This is how it will appear in the output:

.. sidebar:: Sample code representation

    ::

      code sample line 1
      wrapped line 2
      wrapped line 3
          
      new line 2


Tips & Tricks
=============

External References
-------------------

