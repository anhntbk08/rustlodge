Code Flow in Rust
=================

How LLVM Works
++++++++++++++

**LLVM has 3 main parts or stages in compilation :**

- Taking input from the compiler of a high-level language
- Creating IR(Intermediary Representation) from the high level language code
- Giving output as IR to the specified target which is the ISA for binary creation



.. image:: images/llvm.jpeg


How Rust is compiled using LLVM as a backend
++++++++++++++++++++++++++++++++++++++++++++

**Rust high-level code is compiled like this :**

- First, the type checking and borrow checking operations are performed after scanning the code.
- The code is then parsed conforming to the rules. This created an LLVM-IR. The LLVM-IR is platform independent and can be run on any ISA for which the target has been defined in LLVM.
- After that the code is optimized(replacing redundant references, removing comments etc.).
- The Rust compiler then calls LLVM backend which performs semantic analysis and finally creates a binary for the target system.

.. image:: images/RustCodeFlow.png