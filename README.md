# Akari Specification
Testing Framework for HPC Akari  
Solving CPU platform dependency  

Specification of testing framework for porting and optimize Intel x86 Intrinsic function to OpenPOWER

* Current Problem  
There are many SIMD Intel x86 intrinsic function.Intel intrinsic function runs only on Intel,not on OpenPOWER Systems.So we need to port Intel x86 intrinsic code to OpenPOWER equivalent code to run application by good performance on OpenPOWER Systems.But porting Intel x86 Intrinsics to OpenPOWER Intrinsics is technically challenging.

* Obstacle of this project  
Intel x86 Intrinsics and OpenPOWER Intrinsics are not one to one correspondance.PowerISA vector facility(VMX and VSX) are extensive but do not always provide a direct or obvious equivalent to the Intel Intrinsics.Porting must be correct.Error must lead to fatal bug of application.If we can. we want to measure latency and throughput.

* Why we need testing framework  
Result of intrinsics of Intel x86 and OpenPOWER must be equal.If Error or Exception occurres,These must occurre in Intel x86 and OpenPOWER ISA as same.If result is no same,unexpected and unpredictable bug may be occurre.Not reproducable bug may lead to fatal resut.So we must test Intel Intrinsic and currespondance of OpenPOWER ISA automatically.So we need testing framework.

* Structure of testing framework  
Exchange data between Intel x86 and OpenPOWER machine by network or file transfer. Testing framework must be constructed by Python and C language.Input same data in x86 intrinsic function and correspondance of OpenPOWER ISA and compare these output and make sure it is same.


* reference  

Linux on Power Porting Guide: Vector Intrinsics  
https://openpowerfoundation.org/?resource_lib=linux-power-porting-guide-vector-intrinsics  

SLEEF: A Portable Vectorized Library of C Standard Mathematical Functions(Naoki Shibata , Member, IEEE and Francesco Petrogalli 2020)
