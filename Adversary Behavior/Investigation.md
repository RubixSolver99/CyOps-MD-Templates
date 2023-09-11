## Investigation
### Host
***
The user associated with the process is `USER`; this username is associated with a corresponding user in [PeopleFinder](INSERT_LINK). Here is some relevant information:

>INSERT USER INFORMATION FROM PEOPLEFINDER

The endpoint is a member of the following groups:
INSERT GROUPS

### Detection
***
The executable that was terminated was:
>EXCUTABLE PATH

[VT](LINK_TO_VT) shows 0 reports of malicious content and is most likely the legitimate Microsoft Windows executable.

The command that spawned PowerShell was:
>COMMAND RUN FROM COMMAND LINE

The source process was as follows:
>SOURCE PROCESS PATH

This executable was verified by [VT](LINK_TO_VT) to be the legitimate executable from Microsoft Windows as well.

There were 2 commands that were being run as the PowerShell process was terminated. They are as follows:
 - >`C:\WINDOWS\system32\conhost.exe  0xffffffff -ForceV1`
	 - This is a common command for applications running in console mode on Windows.
	 - [VT](LINK_TO_VT) shows 0 reports of malicious content and is most likely the legitimate Windows executable.
 - >`"C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe" /noconfig /fullpaths @"C:\WINDOWS\TEMP\evrvrxq2\evrvrxq2.cmdline"`
	 - A C# compiler command that removes the default config files and references a separate file (`C:\WINDOWS\TEMP\evrvrxq2\evrvrxq2.cmdline`) for additional command-line arguments.
	 - [VT](LINK_TO_VT) shows 0 reports of malicious content and is verified to be the legitimate Windows executable.
 