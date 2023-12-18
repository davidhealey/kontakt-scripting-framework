*************************************************************************
KSP Math Library Version 7.02   7-15-15

V702 of the library compiles with V1.5.2 of the KSE or the equivalent
plugin for Sublime Text 3. Be sureyou have 'Optimize compiled code'
enabled (this also requires that you also have 'Extra syntax checks' enabled.

				 v702
1. Added ExpeVS, Exp2VS, Exp10VS, LogeVS, Log2VS, and Log10VS
2. Added pRange and pRange0
3. Added Clamp, Clamp0, Max, and Min
4. Neg has been deprecated, please use pLT(X,0) in new code

                                 V701

1. Added epDlyTime converter
2. Added comparison predicates pEQ,pNEQ,pLT,pGT,pLTE,and pGTE


                                 V700

1. Added inverse trig functions ACos, ASin, and ATan.

2. Added R2P and P2R for rectanglular to polar and polar to
   rectangular coordinate conversions.

3. Added user selectable, angular unit choices:
     DG - deci-grads     1000 divisions per right angle, Ang90
     CG - centi-grads   10000 divisions per right angle, Ang90
     DD - deci-degrees    900 divisions per right angle, Ang90
     CD - centi-degrees  9000 divisions per right angle, Ang90

4. In addition to Ang90, V700 has constants for Ang180 and Ang360.
   These constants always have the correct value for whatever angular
   unit you specify in SetMathMode. For example, if you specify DD,
   Ang90=900, Ang180=1800, and Ang360=3600. If you specify DG,
   Ang90=1000, Ang180=2000, and Ang360=4000, etc.

5. The X versions of the trig functions have been retired becuase All
   trig functions now accept any input angle: MinInt < Ang < MaxInt.

6. The Library now automatically compiles the pgs callback handler
   needed to support its own initialization. For those applications
   that also need to use the pgs callback, on_pgs_changed is provided
   as a pseudo callback directive.

7. on_post_init (another pseudo callback directive) now makes it
   easier than ever to add application-specific code that needs to
   be executed in the post-initialization phase.

8. The internal support routine for DFmtVal has been recoded more
   efficiently.

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



