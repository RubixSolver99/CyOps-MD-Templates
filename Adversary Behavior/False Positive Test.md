### False Positive Test
Endgame most likely flagged the activity since PowerShell was spawned from `WmiPrvSE.exe` and then continued to spawn 4 new processes, which did use some non-ordinary methods; however, all of the commands being run could be related to, and are most likely to assist in, the uninstallation of Flash Player. 

False Positive Test: Analyst concludes with medium confidence that the alert is a false positive.

Proposed Course of Action: Analyst recommends closing for documentation purposes.