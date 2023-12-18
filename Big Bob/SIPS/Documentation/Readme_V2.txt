

		            README for SIPS Scripts

**********************************************************************************
NOTE: Turn off Word Wrap to read this file in Windows Notepad
**********************************************************************************

Version 2.05    July 15, 2008

This is the Release Version of SIPS 2

V2 of SIPS now contains an Articulation/Alternation Script, the SAS. This new
family member allows you to define and control up to 64 different articulations
per instrument. Articulations can be selected in real time via a dual-bank of
key switches and/or with MIDI program change commands. Each articulation can
control any number of groups which can also be sub-typed and sequenced. Some of
these features work in harmony with the Legato Script's new DFD Offset mode to
provide a convenient solution for the DFD sample-start offset problem. Working
in conjunction with the SAS's Release Group sub-typing, the SLS can also provide
release sample triggering at the end of a legato or portamento phrase. The SAS
also has a very powerful alternation/variation control scheme which can provide
both natural alternation (via group sequencing) and synthesized alternation
using TKT variations. These alternation effects can be controlled in a variety
of very flexible ways similar to that of the Ultra TKT Script but in combination
with natural group-chain alternation.
 
V2 of SIPS adds a new Portamento Mode to the Legato Script. With this mode, you 
can glide or bend between any pair of notes (using any desired-pitch-versus time
contour) with a very realistic, formant-corrected timbre. All the important para-
meters of this mode are MIDI controllable and will enable you to achieve just
about any kind of glissando effect you might want. With the Portamento Mode
engaged, you can now quite literally play an instrument ‘in the cracks’.
 
The control panels have been rearranged to make them more efficient and to make
room for the new functions that have been added. As a part of this ‘face-lift’,
MIDI-Controllable Knobs are now easier to set and they allow more flexible and
precise MIDI subrange control. The subrange of MIDI control for a Knob can be set
to any desired portion of the knob’s full range. For example, if a Knob has a
full range from 0 to 1000 msec, you could set the MIDI Control range to cover
only 0 to 75 ms or perhaps from 900 to 950 ms as you move the MC from min to max.
By reducing the total knob-range of the MC, it can have more resolution where you 
need it most. With V2, setting up such a subrange is very easy to do and requires
no additional controls other than the assigned MC and the Knob itself. And,
since the min and max settings can be interchanged, the MC can now also control
the knob inversely when that is appropriate. 
 
MIDI Controller assignment retains the new scheme adopted with V1.5 of SIPS. You 
simply double-click the MC assignment button to reveal a drop-down menu of
choices. As soon as you click the desired MC in the menu, the assignment is made.
To indicate this, the assignment button is illuminated and displays the MC that
you assigned. In V2, controller choices include the CCs from 0 to 119 plus the
Pitch Wheel, Aftertouch, and Velocity. While the current versions of the KSP still
provide no direct means for a script to detect Aftertouch or Program-Change, V2 of
SIPS (in conjunction with the included custom KSP+ Multiscript), allows you to
assign Aftertouch to control any of its parameters and, the SAS optionally allows
you to select articulations with Program Change commands. 
 
V2 of SIPS provides a new User Preferences Dialog that allows you to customize 
your version of SIPS in a number of useful ways to suit your equipment setup and
style of working. 

ADDITIONAL NOTES for SIPS 2 

I had originally hoped to avoid adding Release Sample triggering to SIPS by
'leaning' on the VXF Script for this function. However, Nils' workload became 
too demanding for him to find the time to update his VXF script (to complete
the interface with SIPS 151). As a result, I decided to add release triggering
to the SLS itself. Because of this and the addition of the new SAS to the Suite,
it will now be fairly easy to create Mod-Wheel X-Fade of velocity layers via
group-control using conventional means. In addition, V205 of the KSP Math Library
now includes a lot of new support functions for group volume control that will 
will facilitate writing a SIPS-Compatible EPXF script. Such a new VXF script
will be able to more easily interface with SIPS because it need only XFade the
velocity groups rather than having to deal with the individual notes (as was
the case with V151).

For release sample triggering, SIPS 2 triggers release samples only for the
last note of a legato phrase. This is the most natural way to handle non-reverby
libraries where such release samples can add an sdditional touch of realism by
supplying actual recorded note closures. However, many owners of reverby libraries,
notably the EW series, had made suggestions that their libraries might benefit
from release sample triggering (at a lower level) for all 'inside' notes of
legato phrases. To give this idea its 'day in court', the initial beta release
of SIPS 2 included an 'experimental' option to implement this idea. But,
unfortunately, beta tester feedback on its performance was not very favorable
and after several back and forth iterations, the idea was abandoned as being
non-workable. Sorry guys, but I tried.

Version 1.5.1 Warning Issued    August 15, 2007

Caution: V150/151 of the SIPS scripts use event parameter 3 to send Script ID info
to the VXF script. Recently it has been discovered that NI is 'secretly' using EP3
to control certain aspects of K2's Release Triggering system. If your instrument
has no RT groups or, if you are using the VXF Script after SIPS, there will be no
conflict with the use of EP3. However, if you are using SIPS (specifically the SLS)
without the VXF script and you are also using an instrument with RT group(s), you
will need to use V2 of the CC/EP Blocker Script V2 in the last slot. Using this
script in the last slot will resolve any conflict in usage of the event parameters.
Please see the Readme file for the CC/EP Blocker Script for more details. 

Version 1.5.1  Release    June 5, 2007

1. Correct default Bend time from 60 cents to 10 cents as for Clarinet 1.
2. Change Offset mode for Clarinet 1 Preset to Manual
3. Revise SVS logic to not require the 'on ui_update' callback so that the SVS
   will operate with K2.1
4. Revised the User's Guide to include an expanded discussion of using the
   the 'Compact Compiler Output' mode of Nils Liberg's KScript Editor.

Version 1.50   May 19, 2007

V1.50 of SIPS employs the new ISCS module and includes the necessary code to
interface with Nils Liberg's VXF Script. Using the ISCS to accomplish this also
prepares for easier interfacing with other scripts in the future.

The Solo-Mode Logic used in the Legato Script has been completely redesigned.
The new logic is much more efficient and easier to understand and maintain. And,
by taking over many of the functions previously relegated to the buggy and
sometimes unpredictable KSP callback triggering and sustain pedal logic, V1.50
will hopefully avoid many of the previously-observed anomalies. For example,
V1.50 should be useable in any script slot (including slot 1) and should also
exhibit a fairly uniform behavior between K2 versions (provided the version you 
are running supports all the necessary user interface elements). A side benefit
of the new solo-mode logic is a reduction in the polyphony requirements. The old
logic required nearly double the polyphony actually needed because of muted notes
that were used (to work-around some KSP quirks). The new Solo-Mode Logic doesn?t 
require such work-arounds and thus requires less polyphony and, more importantly,
doesn't pass any muted notes on to higher scripts. This will further simplify the
task of future integration with other scripts.

Prior versions of the SLS offered two release modes; Knob Setting and Key-Up/BTime.
In the Key-Up/BTime mode, the prior note (the one fading out during the crossfade) 
would begin its note-end release phase when the corresponding key was lifted or
when the BTime setting expired. This latter dependence on BTime was an artifact of
the old Solo-Mode Logic rather than an intended ?feature?. With V1.50, the new logic
eliminates BTime?s involvement. Now the two modes simply begin the release when
the Knob Setting percentage of XTime has been reached (in the Knob Setting mode)
or, when you lift the corresponding key (in the Key-Lift mode). This latter mode is
now independent of the BTime setting (as it should have been all along). 

Assigning a MIDI CC to control various SIPS parameters has been made easier and
more flexible. Instead of an Edit box where you dial in the CC# that you want
(with 0 meaning none and -1 meaning the Pitch Wheel), V1.50 provides a special,
hybrid button-menu (refered to in the User's Guide as an assignment-button) that 
displays the currently assigned CC as a lighted button. However, when you
double-click it a drop-down menu of controllers appears and allows you to select
the desired CC from a list. These menu choices are not only numbered but are also
annotated with their customary MIDI associations (per the MMA). In addition, there
is a 'learn' feature for when you aren't sure which CC# is controlled by some
physical slider or knob on your keyboard.

Once a CC is assigned to control a parameter in one of the SIPS scripts, prior
versions would block further propagation of such assigned CCs. V1.50 no longer
blocks assigned CCs so you can now assign a single CC to control multiple parameters
if you wish (even parameters in two or more separate scripts).

Finally, V1.50 of the SVS has improved upon the way you control the overall Vibrato
Amount. There is now a MIDI-controllable Knob for setting Vibrato Amount as well
as a new drop-down Menu that allows you to select Knob Only, Envelope Only, or
both. These changes should make controlling the overall vibrato intensity much
more intuitive.
***********************************************************************************

Version 1.10   June 23, 2006

V1.10 takes advantage of new features and capabilities in K2.1.1 in a variety of
ways ranging from internal streamlining of the code to cosmetic improvements in
the user interface. K2.1.1 seems also to have solved all previously known issues
reported for V1.05 and V1.051 including the Sonar 'freeze-up' problem, the stuck
notes problem and even the change_vol() noise problem.

Here is the full list of what's new in V110 of SIPS.

1. Source code has been completely updated and made more readable by utilizing
many of the newer features added to the NL Editor since V1.05 of SIPS was released.
The current source code requires V1.0 (or higher) of the NL Editor.

2. Removed GhostTime pause. This was originally used to minimize the KSP hung-note
problem but was causing notes to be dropped occasionally during fast passages. Since
the KSP hung-note problem is no longer an issue, this work-around has been removed.

3. The 'On_When_Lit'enable/disable button has been replaced by a drop-down menu which
adds a script bypass mode that functions just like the KSP Bypass button except that
it can be MIDI controlled.

4. The upper limit of the Vibrato Depth knob has been increased to 5.0 db since
higher values can now be used because of the change_vol() function noise reduction.

5. Because of some of the new control labeling features added in K2.1 and K2.1.1,
Edit-Box labeling has been made less cryptic and units such as % and db have been
added to many of the panel knobs. Also, the RlsFade and Offset knobs now display
a blank data window in the modes where the knob setting is ignored. For example, if
the Offset Mode is set to Auto_1 or Auto_2, the knob's data window is shown as
blank whereas when the Offset Mode is set to Manual Mode or Manual +Rand, the data
window displays the knob's setting in ms.

6. The Instrument Range is now displayed in the letter/octave or 'key' format instead
of as MIDI note numbers. The prompting messages are now displayed on the Set Inst Range
button itself.

7. The internal array used to hold both Built-In and User Presets has been replaced by
two separate arrays; one for Built-In Presets and one for User Presets. This allows the
the User Presets to hold more parameters per preset than V105. It was necessary to open
this up so that User Presets can store all panel parameters instead of just a key-parameter
subset as in V105. This is an essential component in the new Auto-Import Update feature
that will allow easy transfer of full control panels when updating to the latest version
of SIPS.

8. An Auto-Import Update feature has been added that takes advantage of K2.1's double-
buffering of 'persistent' variables. This will allow you to update all your V105 .nkp
and .nki files to V110 and not have to manually re-enter any of the control panel
settings or User Preset data (including the CC assignments and settings).

9. Script ID tagging has been strengthened for this and future releases of SIPS to enable
more reliable typing to prevent illegal data transfer combinations such as from the SVS
to the SLS or preset format downgrading.

10. User Presets can now be re-named.

11. The Import/Export function (which is no longer needed for version upgrading) has
nevertheless been retained in a somewhat simpler form. This additional capability was
retained to allow you to regroup and/or rearrange collections of control panels or presets.

*****************************************************************************************

Version 1.051  April 17, 2006

Fixed sustain pedal problem in the SLS

*****************************************************************************************

Version 1.05   April 15, 2006

This is the initial release version of the
Solo Instrument Performance Suite, SIPS

This initial release of SIPS contains two member scripts:
The SIPS Legato Script, SLS and the SIPS Vibrato Script, SVS.

These scripts attempt to emulate these essential style 'ornaments' and can be used
with any ordinary library instrument, without need for any special types of samples
(such as note transistion pairs, etc). However, if the library instrument you want
to use contains release sample groups, you should delete those first and then resave
the instrument under a new name to distinguish it from the original. See page 28 of
the User's Guide for more details.

                          Known Issues
Unfortunately, there are still known bugs in the KSP and K2. There were also one or
two reported problems that I could never track down. These may or may not be due to
problems with SIPS.

1. The KSP has a known problem with the play_note() function which sometimes results
in hung notes. SIPS has some rather sophisticated code devoted to avoiding this
'KSP Hung Note Problem' but you may still experience some. If so, there is a constant
named $GhostTime that you can edit if you are willing to trade a little latency for
fewer hung notes. For more details, read the header comments of the 'on init' block
for the SLS. This problem is supposedly fixed in NI's long-awaited update.

2. Another known problem with the KSP is noise generated by the change_vol() function.
The SVS uses this function to provide the Depth component of vibrato. The volume
modulations needed for the SVS are rather small and hopefully will not be too
noticeable. The noise is more prevalent for some instruments than others and if you
notice noise artifacts that some have described as begin similar to the old zipper
noise, you will have to reduce the amount of your Depth setting until it no longer
bothers you. Unfortunately, this may sometimes mean setting Depth to zero and doing
without its contribution to the realism. We are all praying that NI has corrected
this problem because it gets in the way of many things we could otherwise do. The
whole PCE project has been on hold for a long time waiting for NI to act.

3. During testing of SIPS it was noticed that there are some problems associated with
the way K2 and the KSP handles the CC123 = 'All Notes Off' message. If the KSP is in
the middle of a tuning operation when a CC123 gets to K2, all events are apparently
retired but the KSP is left in some kind of locked-up state. CC123 messages are
usually sent out from sequencers when they're stopped. To overcome this problem,
a work-around was implemented in SIPS to defer CC123s when they occur during tuning
operations. This fixed all the lock-up problems that I was experiencing but, Theo
Krueger is still having this freeze-up problem intermittently with his setup. At this
time it isn't known if this problem is with SIPS or is caused by some K2/KSP problem
specific to Theo's setup. Since this problem may well be corrected with NI's pending
update, we didn't want to hold up the release of SIPS any longer. However, if you
experience this problem like Theo did, contact him because he has invented a band-aid
work-around that you can use at least until the new NI update.


NOTE: The SIPS Source Code files can be opened and viewed in any plain text editor
such as NotePad.  However, this script was written with User Functions (subroutines)
that cannot be handled directly by the K2 editor. Using subroutines allows the code
to be better organized and easier to read and maintain. The best way to view and/or
print the Source Code is to load it into Nils Liberg's KScript Editor. The NL Editor
will display the Source Code with syntax highlighting for even easier reading. In
addition, once the text has been loaded into the NL Editor, simply hitting the F5 key
will compile the User Functions and place a K2-Ready Script in the clipboard. You can
then paste the clipboard into K2's Script Editor where it can be compiled and run.

The SIPS Scripts are also provided as K2 .nkp files. If you don't have the NL Editor
(although you should get a copy for yourself since Nils has graciously made it
available to us free), you can still produce a K2-Ready Source Code file as follows.
Install the .nkp file per the instructions on page 29 of the SIPS User's Guide. Then,
load an instrument into K2 and then load the SIPS Scripts. Load the SLS in the first
tabbed script position and load the SVS in the 2nd tabbed script position. Since the
.nkp files aren't password locked, you can now open the K2 Editor and view the source
code for either script (in K2 format). In fact, you can select the code in K2's editor
and copy it to the clipboard for pasting into Notepad. You can then view, print, or save
this K2-Ready form of the Source code if you like (but it's a lot messier to read).	   