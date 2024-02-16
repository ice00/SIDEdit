# SIDEdit
SIDedit - A Perl/Tk GUI based application to read and edit binary SID files.

## DESCRIPTION

This Perl/Tk GUI application allows the user to read, write and edit
binary SID files, which are music player and data routines converted
from the Commodore-64 computer with an additional informational header
prepended. SIDedit has become a useful tool for people ripping SID tunes
out of Commodore-64 executables.

Most of the application's common functions should be obvious, and for
some of the less obvious ones tooltips provide additional hints.

This tool is intended for programmers, SID rippers, or other people with
reasonable background. It is not suitable for newbies who have never
before used hexadecimal numbers, who are not familiar with the
Commodore-64 computer's internals or with the SID file format (click
Help -> SID file format description on the menu for the format
specification).

## PREREQUISITES

This script requires the following modules:

    Audio::SID

    Cwd

    File::Basename

    File::Copy

    Switch;

    Tk

    Tk::Balloon

    Tk::Checkbutton

    Tk::Dialog

    Tk::DialogBox

    Tk::Optionmenu

    Tk::Radiobutton

    Tk::ROText

    Tk::BrowseEntry

    Tk::LabFrame

    Tk::Scrollbar

    Tk::Button

    Tk::Entry

    Tk::Photo

    Tk::ToolBar

    Tk::NoteBook

    Tk::WaitBox
    
    Tk::DirTree

On Win32 machines it also uses these modules:

    Win32

    Win32::API

    Win32::Process

    Win32API::File

## KNOWN BUGS

* Data display rendering and clipboard operations are way too slow with colors
(try new Perl/Tk?).

* Under UNIX bringing up the display data window caused a grab fail.
(Bug in Perl/Tk?)

* On some systems if you press down on the mousewheel button and move down,
the SID data scrolls up, and moving up scrolls down (it should be the other
way around).
(Bug in Perl/Tk.)

* There's a problem with the scrollbar on the data display window when
"assembly" is selected: it doesn't always scroll all the way down when grabbed
with the scrollblock.
(Bug in Perl/Tk.)

* Checked items in the menu partially cover first letter of menu entry.
(Bug in Perl/Tk.)

* After selecting File->New last file doesn't get deselected in the filelist.
(Bug in Perl/Tk - can't deselect from listbox.)

If you find any other bugs in this program, please, report them to the
author (see below).

## TO DO LIST

* Disassembly rendering (when jumping to address or switching views) should
always re-start at proper address (instead of in the middle of an
instruction).

* RunTool execution should have a WaitBox.

* Restrict Play SID file to actual SID/INFO files only.

* DirTree browser doesn't quite work in Win32. Try chooseDirectory instead?

* Add key bindings to Configure settings popup.

* Add popup to show quick summary of assembly codes.

* Add File -> Open... (rip out a Load function from FileSelect).

* Add "Load data" to SID data display.

* I'd like to have SIDedit remember the last x directories I worked in.
Sometimes I quickly need to change between my rip directory and the HVSC
directory to compare something, so it would be nice to implement a similar
history function as in the RUN TOOL window. (Add <- and -> nav buttons!)

* Optimize Load/Save Settings code (hash! - use Config::IniHash or sg).

* Optimize Settings screen code (map!).

* Add right-click menu to file navigator. Prune right-click menu on SID data
and text display? (Selection problem!)

* Add mm file analyzation support, see SidUsage files!

* Change "name" field to "Title" (In Audio::SID, too).

* Add an info field to "Show SID Data" that shows which SID player engine is
used.

* Add option to allow users to revert back to standard copy/paste operations
(i.e. select a field, copy it). (BUT: $window->clipboardPaste() doesn't work,
neither does $window->insert - great...)

* Add a button called "Batch processing". In there one option would be to
generate a text output of checked fields recursively in current dir, another
option would be to change the checked fields in all files recursively to what
is in current file.

* Simon: I still wish something could be done about it like say combining load
address and range (make load address always reflect the range start address).
Then by changing load address you'll see the range change.  Also might be nice
if you then click display data the new load address is used...  You could even
combine load address and range into a single line.

* Keep the ShowSIDData and ShowTextOutput windows on screen, don't grab, so they
can be displayed side-by-side.

* Add Dag's code to fill out startPage and pageLength automatically.

* Add ability to recurse dirs and autoconvert SID files as per specified
options.

* Load MD5s from expanded Songlengths DB to find SIDs already in HVSC.

* Allow siddiag duplicate match against HVSC. Or in general incorporate a
duplicate finder?

* Add ability to search every field of every SID found in HVSC and/or other
specified directories. Sort of like SidBace. Build a text DB for this. Add
search capability for Songlength DB, STIL, etc.


## VERSION

    SIDedit v4.02

    Modified to allow compilation with up to date Perl and Audio::SID library.

## SEE ALSO

    *   LaLa's SID pages for the latest version of SIDedit:

        http://lala.c64.org

    *   The High Voltage SID Collection, the most comprehensive archive of
        SID tunes:

        http://www.hvsc.c64.org

    *   Audio::SID
