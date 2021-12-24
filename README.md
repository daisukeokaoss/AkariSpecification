# AkariSpecification
Testing Framework Akari Specification

Specification of testing framework for porting Intel x86 Intrinsic to OpenPower

* Current Problem  
There are many SIMD Intel x86 intrinsic function.Intel intrinsic function runs onlyy on Intel,not on OpenPOWER Systems.So we need to port Intel x86 intrinsic code to OpenPOWER equivalent code to run application by good performance on OpenPOWER Systems.But porting Intel x86 Intrinsics to OpenPOWER Intrinsics is technically challenging.

* Obstacle of this project  
Intel x86 Intrinsics and OpenPOWER Intrinsics are not one to one correspondance.PowerISA vector facility(VMX and VSX) are extensive but do not always provide a direct or obvious equivalent to the Intel Intrinsics.Porting must be correct.Without error must lead to fatal bug of application.If we can. we want to measure latency and throughput.
