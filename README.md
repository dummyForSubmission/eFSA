# eFSA 
=====Accompany materials for event driven anomaly detection in CPS systems=====

The dummy repository provides accompany materials that are only used for the anonymous submission.

The full project, code, and author information are anonymized.

## Traces
We provide Sample traces from the real-world CPS applications (please see the Sample Traces folder). 
We use the system tool strace-4.13 to intercept system call of a running program. 
The figure shows an example of using strace tool with stack unwinding support. In this example, we use the PC value of relative address 0x43c for the write system call. As a result, system calls that are triggered from different places in the program will be associated with different PC values.

<img src="https://github.com/dummyForSubmission/eFSA/blob/master/figures/unwindsyscall.png" height="130" width="350">


## Event Program Analysis
Our event dependence analysis tool is implemented within the Low Level Virtual Machine (LLVM) compiler infrastructure, based on an open source <a href="https://github.com/mchalupa/dg">static slicer</a> which builds dependence graph for LLVM bytecode.
The following figure illustrates an example our LLVM-based dependence analysis tool. Given the line number of an event of interest (e.g., line 8), we obtain the line numbers of statements which are directly data dependent or control dependent on the event, where the black line represents direct data dependence, and the blue line indicates direct control dependence. From semantics of the LLVM’s br instruction, label 0 indicates a predicate returns true. Therefore, we know that the event dependent statements are lines 9 and 10 of the example code. 

<img src="https://github.com/dummyForSubmission/eFSA/blob/master/figures/eventdependencyanalysis.png" height="200" width="350">


## Sample Data-oriented Attack in the SyringePump application

<img src="https://github.com/dummyForSubmission/eFSA/blob/master/figures/SyringeBufferOverflow.png" height="400" width="400">

