		Readme File, for KSP Math Library 
		           V215  March 2009

This release adds a number of useful format-conversion routines, bringing the total to 18 (not counting the legacy Get_db and the CVHex utility). VR_to_mdb was altered to use the fast Log10 routine instead of the extended XLog10 routine. With this release, the Get_db routine is now provided for backward compatibility only. New scripts should always use VR_to_mdb because it will execute faster and has a greater operating range.

In V210, some of the format-conversion routines included code to 'clamp' the input or output to the operating range for the routine. For V215, all such limit clamping code was removed to make the routines leaner and meaner for the majority of situations. Thus it is assumed that your script will not attempt to use these routines outside of their usual operating range. If you need to use one of these format-conversion routines in a context where the valid input range might be exceeded (and you want to prevent this), your script will need to provide any needed limit testing and clamping. None of the routines will do anything crazy if you exceed their normal input range, but, the results returned may or may not be correct (depending on the routine and how far out of range you are). Please refer to the header comments of the individual routines for more information.

In addition, minor changes have been made to some of the format-conversion routines to improve their arithmetic accuracy slightly. So, in some cases, you may notice a small difference in the output for a given input (usually toward more accuracy) for these routines compared with their V210 counterparts.

The main library header comments have been revised and information on Input/Output parameter passing has been added. Please read this carefully to avoid any problems with using the library routines. Minor updates and corrections were made to the User's Guide to bring it current. The Technical Guide has been extensively revised and expanded. It now includes a new section 6.0 which discusses the details of how the format-conversion routines are coded.

Prior Version Summary

V210  January 2009
The cube root routine, Root3, and the Pitch_to_ep format-conversion routine was added. The documentation was revised and updated. Execution time benchmarks were added to the Technical Guide. A test utility routine was also added to enable easy display of numbers in hexadecimal.

V200..205  April 2008
V200 with some minor revisions through V205, added several new basic functions including the extended-precision Log and the Exponential routines. In addition, four more format-conversion routines were added.

The User's Guide and Technical Guides were revised and expanded. A second EPXF Tutorial was added to the User's Guide to demonstrate how to perform EPXF via engine parameter control of groups.

V105  December 2006
This was the first 'official' release of the KSP Math Library Package. It contained the trig and fast log functions, ATFade and one format-conversion routine, Get_db.

Documentation included the User's Guide (with the first Equal-Power Crossfade Tutorial) and the Technical Guide for the included functions.