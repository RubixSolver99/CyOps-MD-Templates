## Investigation
### Host
***
The user associated with the process is `SYSTEM`; this is the default system user for Microsoft Windows, which does not provide any additional information.

Another user associated with the target process was `yizhang`; here is relevant information from [PeopleFinder](https://apps.cyber.tamus.edu/people_finder/directory/tamu/yizhang/):
>display_name: 	Zhang, Yi
first_name: Yi
last_name: Zhang
title: Graduate Assistant - Research
department: Teaching, Learning and Culture (Tlac)

The endpoint is a member of the following groups:
PVAMU | PVAMU-WS

### Detection
***
The executable that was terminated was:
>C:\Program Files (x86)\Citrix\ICA Client\inject.exe

[VT](https://www.virustotal.com/gui/file/13c328e45613a74e55b12e05c4a166a26216fc8950d466ac54d8c131dd2410cf) shows 0 reports of malicious content.

The command that attempted injection was:
>`"C:\Program Files (x86)\Citrix\ICA Client\inject.exe" inject "C:\Program Files (x86)\Citrix\ICA Client\epclient32.dll" "C:\Program Files (x86)\Citrix\ICA Client\epclient64.dll"`

[epclient32 DLL's](https://www.file.net/process/epclient32.dll.html) are commonly associated with Citrix software.

The source process was as follows:
>C:\Windows\System32\msiexec.exe

This executable was verified by [VT](https://www.virustotal.com/gui/file/0a8797d088023a7f17bb00b22ff7c91036070cca561bff5337c472313c0cb4ad) to be the legitimate executable distributed by Microsoft Windows.

The target process was:
>C:\Program Files\Websense\Websense Endpoint\Dserui.exe

[VT](https://www.virustotal.com/gui/file/5d7ba3e2475974ea713a6ee77f523e75289f64611ca3aed8777f8fd4a742218b) shows 0 reports of malicious content.

This is a common executable for Websense Endpoint protection software. It has been rebranded/re-acquired by [ForcePoint](https://www.forcepoint.com/?utm_source=Websense&utm_medium=Redirect&utm_content=home).