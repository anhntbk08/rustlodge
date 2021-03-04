Git Plumbing System
+++++++++++++++++++++++++++++++++++++++++++

The Git Plumbing system has the following major parts:

- **Objects** ``(dir)``: store all the content for the database
- **Refs** ``(dir)``: store pointers into commit objects in that data (branches)
- **HEAD** ``(file)``: points to the branch you currently have checked out
- **Index** ``(file)``: stores your staging area information and acts like a temporary snapshot for the repo


.. image:: images/plumbing1.jpg

Demonstrating Simple Git Plumbing Commands
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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


Adding files to the index

In Git, the index or staging area is a temporary snapshot of your repository. It’s a collection of files that
have been modified, but not yet saved to the permanent history. In a porcelain Git workflow, you add files
to the index with git add, then take a snapshot of the index with git commit. With plumbing, there are
several extra steps.

We can save a file to the index with the update-index command:

.. code-block:: bash

    git update-index --add sample.txt

.. note:: Note that if you haven’t saved a file already with hash-object, it’s done automatically for you.


If we look in the .git directory, there’s a new file index:

.. code-block:: bash

    ls .git


We can see what we’ve added to the index with the plumbing command ls-files:

.. code-block:: bash

    git ls-files


Taking a permanent copy of the index

To take permanent copies of the snapshot, we need another plumbing command: write-tree:

.. code-block:: bash

    git write-tree


We’ve got back a hash – this is another Git object!


.. code-block:: bash


    find .git/objects -type f


Let’s inspect it with cat-file:

.. code-block:: bash

    git cat-file -p dc6b8ea09fb7573a335c5fb953b49b85bb6ca985

.. code-block:: bash

    ❯ git cat-file -p a79dae98a3c7b0299544270733ae9b0b920ffe72
    100644 blob 18a4906282bd994b870b651a00b9d421e4df4a99	sample.txt


.. code-block:: bash

    ❯ git cat-file -t a79dae98a3c7b0299544270733ae9b0b920ffe72
    tree



.. code-block:: bash

    ❯ git cat-file -t 18a4906282bd994b870b651a00b9d421e4df4a99
    blob



.. note:: A blob object stores the contents of a file, but doesn’t know what the file is called.
          Those are what we created in part 1. Now we’re creating tree objects, which know what files are called.
          A tree can point to a blob to describe the file contents.



.. image:: images/blob_tree.png




















































































