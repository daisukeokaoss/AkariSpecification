# Testing Framework Akari Specification

[Development Discord Server](https://discord.gg/J6DgQcGEPf)

Testing Framework for HPC  
Solving CPU platform dependency  

Specification of testing framework for porting and optimize Intel x86 Intrinsic function to OpenPOWER

* Current Problem  
Intel x86-64 CPU are everywhere. From laptop PC to supercomputer. Intel x86-64 is CISC(Complex Instruction Set Computer) and very long history. And once code runs on Intel x86-64, it must run Intel forever. So Intel carries a lot of past heritage.
On the other hand,IBM Power and ARM are RISC(Reduced Instruction Set Computer) and its same in the aspect of “it runs once, it must run forever” but instruction set are simple and RISC can use relatively new technology.
So many supercomputer use RISC.
But No 1 of market share of supercomputer is Intel because many Linux application is made for Intel.
So if  application for Intel x86-64 can run RISC like ARM or OpenPOWER by very optimized way. It’s great advancement of Computer Science and Technology.

There are many SIMD Intel x86 intrinsic function.Intel intrinsic function runs only on Intel,not on OpenPOWER Systems.So we need to port Intel x86 intrinsic code to OpenPOWER equivalent code to run application by good performance on OpenPOWER Systems.But porting Intel x86 Intrinsics to OpenPOWER Intrinsics is technically challenging.

* Obstacle of this project  
Intel x86 Intrinsics and OpenPOWER Intrinsics are not one to one correspondance.PowerISA vector facility(VMX and VSX) are extensive but do not always provide a direct or obvious equivalent to the Intel Intrinsics.Porting must be correct.Error must lead to fatal bug of application.If we can we want to measure latency and throughput.

* Why we need testing framework  
Result of intrinsics of Intel x86 and OpenPOWER must be equal.If Error or Exception occurres,These must occurre in Intel x86 and OpenPOWER ISA as same.If result is no same,unexpected and unpredictable bug may be occurre.Not reproducable bug may lead to fatal resut.So we must test Intel Intrinsic and currespondance of OpenPOWER ISA automatically.So we need testing framework.

* Structure of testing framework  
Exchange data between Intel x86 and OpenPOWER machine by network or file transfer. Testing framework must be constructed by Python and C language.Input same data in x86 intrinsic function and correspondance of OpenPOWER ISA and compare these output and make sure it is same.

* Connect Intel and OpenPower by Python network framework  
Install Web API on Intel and connect from OpenPower using SSH  



reference  

Linux on Power Porting Guide: Vector Intrinsics  
https://openpowerfoundation.org/?resource_lib=linux-power-porting-guide-vector-intrinsics  

SLEEF: A Portable Vectorized Library of C Standard Mathematical Functions(Naoki Shibata , Member, IEEE and Francesco Petrogalli 2020)
