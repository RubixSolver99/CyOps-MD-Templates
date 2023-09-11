## Investigation
### Host
***
The user associated with the process is `abablee`; this username and similar combinations of first and last names resulted in no results being found in PeopleFinder, the PVAMU Directory or in the TAMU Directory.

The endpoint is a member of the following groups:
PVAMU | PVAMU-WS

### Detection
***
The following file was flagged malicious by Endgame:
>C:\Users\abablee\PCAppStore\AutoUpdater.exe

VT returned 0 results for the hash or the filename.

The source process was as follows:
>C:\Users\abablee\PCAppStore\setDRM.exe

This executable shows 5 reports of malicious content on [VT](https://www.virustotal.com/gui/file/57c643a3e1c6be6407eb7f127b5c3168e9c42be49d0adb574f02e834435fd5ea).

The command run was:
>"C:\Users\abablee\PCAppStore\setDRM.exe" 1693932131911541

This command appears to be a basic one that takes a single argument. No amount of Google-ing or searching revealed many results for the executable or number that was passed as an argument. 