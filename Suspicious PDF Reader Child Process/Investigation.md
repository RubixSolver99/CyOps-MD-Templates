## Investigation
### Host
***
The user associated with the process is `laurenerickson`; here is some relevant information from [PeopleFinder](https://apps.cyber.tamus.edu/people_finder/directory/tamu/laurenerickson):
>display_name: Erickson, Lauren
first_name: Lauren
last_name: Erickson
title: IT Generalist I
department: Technology Services

The endpoint is a member of the following groups:
ENGR | TEES | TEES-WS

### Detection
***
The following executed was flagged as a suspicious PDF child process:
>C:\WINDOWS\system32\msiexec.exe

[VT](https://www.virustotal.com/gui/file/aa2fa1000f9fea03339edf67295dd043806294ec1644e38b7dd08e7d670d5423) shows 1 report of malicious content, but is most likely still the legitimate Windows executable.

The source process was as follows:
>C:\Program Files\Adobe\Acrobat DC\Acrobat\Acrobat.exe

The hash for this executable was not recorded, but based on the file path and name, it is likely the authentic Adobe Acrobat.

The command run was:
>`C:\WINDOWS\system32\msiexec.exe /I {AC76BA86-1033-FFFF-7760-BC15014EA700} REINSTALL="ALL" REINSTALLMODE="omus" /qb`

This command is used to reinstall what is most likely Adobe Acrobat (some evidence of matching product codes, but unable to verify). Here is a breakdown of the command arguments:
>REINSTALLMODE="omus": This parameter defines the reinstallation mode. The different letters in the value have specific meanings:
o: Reinstall if the file is missing or is an older version.
    m: Reinstall all files, regardless of the version.
    u: Rewrite all required user-specific registry entries.
    s: Reinstall all shortcuts and re-cache them.
/qb: This is a user interface (UI) option that controls the level of interaction during the installation. In this case:
    /q: Specifies a basic UI level, which shows a modal dialog box with a progress bar.
    /b: Specifies to display a modal dialog box at the end of the installation.