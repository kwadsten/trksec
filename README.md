# trksec


Like many others, I have always wanted to write TRS-80 assembly language programs.  More specifially, a TRS-80 game.  Even though there are many good books and resources available, it is still fairly difficult to get anything substantial working.

While working on my game (granted slowly), I started thinking about interrupts and how they might be useful in my game - perhaps for handling input or even animation tasks.  The first order of business was to research interrupts on the TRS-80.  

To my surprise, I found very little information on TRS-80 interrupts and almost no example code to use them.  What I did find seemed to indicate that the real-time clock interrupt is probably the easiest (only?) one to work with.  The Model 1 (with expansion interface), the Model III, and the Model 4/4p all have a real-time clock interrupt that fires every 1/30th of a second (30hz).  

My best resource was the book "MOD III ROM COMMENTED" by Soft Sector Marketing (1981).  This a fantastic book and an invaluable resource for this project.  A pdf can be found on the internet archive.

DISCLAIMER:  I'm new to interrupts and z80 coding in general.  Some or all of this information may be misleading or incorrect.  The code works but may not work for your particular application.  

This application (**trksec**) shows a real-time display of the current track and sector being accessed by the disk drive.  The display is in the upper-right corner of the display just to the left of the standard DOS CLOCK display.  Please note that the drive number being access is not displayed.  trksec is compatible with the DOS CLOCK command.

**trksec** runs on a Model III under TRS-DOS 1.3.  The interrupt vectors for other DOS'es will most likely be different.  Also note that trksec is loaded in "high-memory" ($F000) to avoid conflict with other applications.  Users with less RAM will need to modify this starting address.  I used the great zmac assembler to compile and trs80gp emulator to run and debug. 

Note:  Some DOS functions actually clear all of upper memory after they run (ie. the DOS LIST command).   With some research and patience these routines could be found and patched to prevent clearing of upper memory.

[MOD III ROM COMMENTED (pdf)](https://archive.org/details/Model_III_ROM_Commented_1981_SSM)

[zmac assembler](http://48k.ca/zmac.html)

[trs80gp emulator (macOS & Windows)](http://48k.ca/trs80gp.html)