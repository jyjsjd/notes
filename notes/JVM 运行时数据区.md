---
title: JVM 运行时数据区
created: '2019-05-12T02:48:18.322Z'
modified: '2019-05-12T02:59:34.960Z'
tags: [Java]
---

# JVM 运行时数据区

## pc Register

 Each JVM **thread** has its own pc (*program counter*) register. At any point, each Java Virtual Machine thread is executing the code of a single method, namely the current method for that thread. 
 
 - If that method is *not native*, the pc register contains the address of the Java Virtual Machine instruction currently being executed. 

 - If the method currently being executed by the thread is *native*, the value of the Java Virtual Machine's pc register is *undefined*. 

## JVM Stack

Each JVM **thread** has a private Java Virtual Machine *stack*, created at the same time as the thread. A Java Virtual Machine stack stores *frame*s.

- If the computation in a thread requires a larger JVM stack than is permitted, the JVM throws a StackOverflowError.

- If JVM stacks can be dynamically expanded, and expansion is attempted but insufficient memory can be made available to effect the expansion, or if insufficient memory can be made available to create the initial JVM stack for a new thread, the JVM throws an OutOfMemoryError.

## Heap

The JVM has a heap that is shared among **all** JVM threads. The heap is the run-time data area from which memory for all *class instance*s and *array*s is allocated.

## Method Area

The JVM has a method area that is shared among **all** JVM threads. It stores per-class structures such as the run-time constant pool, field and method data, and the code for methods and constructors, including the special methods used in class and instance initialization and interface initialization.

## Run-Time Constant Pool

A run-time constant pool is a per-class or per-interface run-time representation of the **constant_pool table** in a class file. It contains several kinds of constants, ranging from numeric literals known at compile-time to method and field references that must be resolved at run-time. The run-time constant pool serves a function similar to that of a symbol table for a conventional programming language, although it contains a wider range of data than a typical symbol table.

## Native Method Stack

An implementation of the JVM may use conventional stacks, colloquially called "C stacks," to support native methods
