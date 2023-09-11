## Investigation
### Host
***
The user associated with the process is `SYSTEM`; this is the default Windows system user.

The endpoint is a member of the following groups:
PVAMU | PVAMU-WS

### Detection
***
The executable that was terminated was:
>C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe

[VT](https://www.virustotal.com/gui/file/b4e7bc24bf3f5c3da2eb6e9ec5ec10f90099defa91b820f2f3fc70dd9e4785c4) shows 0 reports of malicious content and is most likely the legitimate Microsoft Windows executable.

The command that spawned PowerShell was:
>"C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -ExecutionPolicy  Bypass .\Uninstall-AdobeFlash.ps1 -DeploymentType "Uninstall" -DeployMode "NonInteractive"

The source process was as follows:
>C:\Windows\System32\wbem\WmiPrvSE.exe

This executable was verified by [VT](https://www.virustotal.com/gui/file/2198a7b58bccb758036b969ddae6cc2ece07565e2659a7c541a313a0492231a3)  to be the legitimate executable from Microsoft Windows as well.

There were 4 commands that were being run as the PowerShell process was terminated. They are as follows:
 - >`C:\WINDOWS\system32\conhost.exe  0xffffffff -ForceV1`
	 - This is a common command for applications running in console mode on Windows.
	 - [VT](https://www.virustotal.com/gui/file/da6bdc166a616a0f292e12d05f91658f5e96a0273bafce4e9334c7890c0f9cd6) shows 0 reports of malicious content and is most likely the legitimate Windows executable.
 - >`"C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe" /noconfig /fullpaths @"C:\WINDOWS\TEMP\evrvrxq2\evrvrxq2.cmdline"`
	 - A C# compiler command that removes the default config files and references a separate file (`C:\WINDOWS\TEMP\evrvrxq2\evrvrxq2.cmdline`) for additional command-line arguments.
	 - [VT](https://www.virustotal.com/gui/file/4a6d0864e19c0368a47217c129b075dddf61a6a262388f9d21045d82f3423ed7) shows 0 reports of malicious content and is verified to be the legitimate Windows executable.
 - >`"C:\WINDOWS\ccmcache\9\Files\uninstall_flash_player.exe" -uninstall`
	 - This is a simple executable for uninstalling Flash Player.
	 - [VT](https://www.virustotal.com/gui/file/a967fe37132dfc787f3df0c6836ad7b44abc209826cbf34564ecafc0ff229a2b) shows 0 reports of malicious content and is most likely the legitimate Windows executable.
 - >`"C:\WINDOWS\System32\msiexec.exe" /x "{A13B841B-2210-4C3F-BB15-6662AE50AF39}" REBOOT=ReallySuppress /QN /L*v "C:\WINDOWS\Logs\Software\Adobe_AdobeFlashPlayer32ActiveX_32.0.0.270_Uninstall.log"`
	 - This runs the windows uninstaller for the specified software with the product code: `A13B841B-2210-4C3F-BB15-6662AE50AF39`.
		 - This product code does match Flash Player's MSI GUID for v32.0.0.270 found on [Adobe's Website](https://helpx.adobe.com/ua/flash-player/kb/msi-guids-windows.html).
	 - [VT](https://www.virustotal.com/gui/file/aa2fa1000f9fea03339edf67295dd043806294ec1644e38b7dd08e7d670d5423/detection) shows 1 report of malicious content, but is still most likely the legitimate Windows executable.