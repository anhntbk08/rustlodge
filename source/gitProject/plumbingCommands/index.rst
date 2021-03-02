Git Plumbing System
+++++++++++++++++++++++++++++++++++++++++++

The Git Plumbing system has the following major parts:

- **Objects** ``(dir)``: store all the content for the database
- **Refs** ``(dir)``: store pointers into commit objects in that data (branches)
- **HEAD** ``(file)``: points to the branch you currently have checked out
- **Index** ``(file)``: stores your staging area information and acts like a temporary snapshot for the repo


.. image:: images/plumbing1.jpg

Demonstrating Simple Git Plumbing Commands
+++++++++++++++++++++++++++++++++++++++++++

**Git Objects**

Make a repo:


.. code-block:: bash

    mkdir plumbing-repo
    cd plumbing-repo

Initialize an empty git repo:

.. code-block:: bash


    git init

See the contents:

.. code-block:: bash

    ls .git


Create a file

.. code-block:: bash

    echo "This is a sample file for testing git plumbing" > sample.txt

Hash the file

.. code-block:: bash

    git hash-object -w sample.txt

Find the hashed file:

.. code-block:: bash

    find .git/objects -type f

Cat the file with its hash:

.. code-block:: bash

    git cat-file -p 18a4906282bd994b870b651a00b9d421e4df4a99


**Blobs and Trees**
































