*************************************************************************
KSP Math Library Version 6.10   1-22-14

V610 of the library compiles with V1.5.2 of the KSE or the equivalent
plugin for Sublime Text 3 .


                                 V610
1. Fixed an initialization issue that affected some computer systems.

2. Improved the internal _NLZ routine (Number of Leading Zeros) used
   by many of the library's normalization routines. New version runs
   about 10% faster and now covers the full range from 0 to 32 leading
   zeros.

3. Added a new conditional predicate Sign3.

4. Added XOR function. This is a one-line functions that returns the
   exclusive OR of two input integers (bit by bit).

                                 V600
1. V600 provides another major overhaul of the Fast Math mode. This
implementation requires no NKA files at all (before, after, or during
development).The lookup tables are now automatically initialized by the
library itself during normal initialization. All that you need do to
switch from Standard to Fast mode or vice versa is to change the
corresponding compiler switch. Please see Section 4 of the User Guide.

2. The User's Guide has been significantly revised for V600. Please be
sure to read at least sections 2 and 4 to familiarize yourself with the
main differences from prior versions of the library.

*************************************************************************



