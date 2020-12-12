Git from Source
===============

1. Install Git essential
------------------------

    .. code-block:: html
    
        sudo apt install git build-essential

2. In browser got to `Git via Git <https://git-scm.com/downloads>`_
-------------------------------------------------------------------

    * you can get the latest development version via Git itself

    
    .. code-block:: html
    
        git clone https://github.com/git/git

3. Go into git dir.
-------------------


    .. code-block:: html
    
        cd git

4. Run ``make config``  
----------------------

    .. code-block:: html
    
        make configure

5. Update and Install Dependencies
----------------------------------

    .. code-block:: html
    
        sudo apt install libz-dev libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext cmake gcc

6. Go into git dir & run make all
---------------------------------

    .. code-block:: html
    
        cd git

        make all


7. Run make install 
-------------------

    .. code-block:: html
    
        make install

8. Check out all the executable files are existing in the bin dir
-----------------------------------------------------------------

    .. code-block:: html
    
        ls /home/{USERNAME}/bin

9. Check git version in the git dir
-----------------------------------


    .. code-block:: html
    
        /home/{USERNAME}/bin/git --version
        
10. Check git version on the base
---------------------------------

    .. code-block:: html
    
        git --version