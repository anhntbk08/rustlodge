Binary vs Library
#################

Library
+++++++

A static library is used if you intend to utilize your generated code as a piece of a larger application on your
hardware. In this case, you would likely be writing some other Rust code by hand or already have some code which
will be run on the hardware and want to leverage your project code in that larger application. A static library
does not require a main function. You would rather link it with your other code and call the generated functions
from that code.

Binary
++++++

An binary is just that, a complete binary which can be run on its own. You would likely want to use this
if you have the entirety of your application written in the project and want to run the whole thing on your hardware.
Creating a binary requires writing and supplying a main function as that main function is how the operating
system knows to run the binary.


.. image:: images/binaryVsLibrary.jpeg