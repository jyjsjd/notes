---
title: Garbage Collection Roots
created: '2019-01-28T09:12:33.876Z'
modified: '2019-01-28T09:16:07.343Z'
tags: [Java]
---

# Garbage Collection Roots

A garbage collection root is an object that is accessible from outside the heap. The following reasons make an object a GC root:

* **System Class** 
Class loaded by bootstrap/system class loader. For example, everything from the rt.jar like java.util.* .
* **JNI Local**
Local variable in native code, such as user defined JNI code or JVM internal code.
* **JNI Global**
Global variable in native code, such as user defined JNI code or JVM internal code.
* **Thread Block**
Object referred to from a currently active thread block.
* **Thread**
A started, but not stopped, thread.
* **Busy Monitor**
Everything that has called wait() or notify() or that is synchronized. For example, by calling synchronized(Object) or by entering a synchronized method. Static method means class, non-static method means object.
* **Java Local**
Local variable. For example, input parameters or locally created objects of methods that are still in the stack of a thread.
* **Native Stack**
In or out parameters in native code, such as user defined JNI code or JVM internal code. This is often the case as many methods have native parts and the objects handled as method parameters become GC roots. For example, parameters used for file/network I/O methods or reflection.
* **Finalizable**
An object which is in a queue awaiting its finalizer to be run.
* **Unfinalized**
An object which has a finalize method, but has not been finalized and is not yet on the finalizer queue.
* **Unreachable**
An object which is unreachable from any other root, but has been marked as a root by MAT to retain objects which otherwise would not be included in the analysis.
* **Java Stack Frame**
A Java stack frame, holding local variables. Only generated when the dump is parsed with the preference set to treat Java stack frames as objects.
* **Unknown**
An object of unknown root type. Some dumps, such as IBM Portable Heap Dump files, do not have root information. For these dumps the MAT parser marks objects which are have no inbound references or are unreachable from any other root as roots of this type. This ensures that MAT retains all the objects in the dump.
