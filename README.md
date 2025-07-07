# ILEA-2025-Memory-Capture-Analysis

AVML (Linux)
> https://github.com/microsoft/avml

Belkasoft Live Ram Capture (Win)
> https://belkasoft.com/ram-capturer

Cederpelta (Mac/Linux)
> https://www.brimorlabsblog.com/2019/04/live-response-collection-cedarpelta.html

FTK Imager (Win)
> https://www.exterro.com/digital-forensics-software/ftk-imager

Magnet Ram Capture (Win)
> https://www.magnetforensics.com/resources/magnet-ram-capture/

Oracle VirtualBox
> https://www.virtualbox.org/

REMnux (malware analysis virtual machine)
> https://remnux.org/

Volatility3
> https://github.com/volatilityfoundation/volatility3

-----
-----
SANS Memory Forensics Cheat Sheet 3.0
> https://sansorg.egnyte.com/dl/4QwNVeoj02

-----
-----
Memory Capture Workflow with Volatility3 using a REMnux Virtual Machine

Additional command arguments:
> vol3 -q -r pretty -f WIN10.mem windows.netscan.NetScan > NetScan.txt
>> (-q = run without status bar)
>> 
>> (-f = use the following memory file to scan)
>> 
>> (-r pretty = renders the text lined up in each column)
>> 
>> (>= output to file name fm-tetris.netscan.txt)
    

Windows Info: system information
> vol3 -f Win10.raw windows.info.Info

PsList: Lists process IDs and parent process IDs (faster than psscan, can miss hidden processes)
> vol3 -f Win10.raw windows.pslist.PsList

PsScan: Lists process IDs and parent process IDs (slower than pslist, finds hidden processes)
> vol3 -f Win10.raw windows.psscan.PsScan

DllList: Lists all loaded dlls (review legitimate dlls, and possible malicious, review locations "temp")
> vol3 -f Win10.raw windows.dlllist.DllList

CmdLine: lists process and command line arguments (may be able to link a process ID/connection IP to an .exe)
> vol3 -f Win10.raw windows.cmdline.CmdLine

NetStat: reviews network info for connections, ports, and PID (fast, may miss hidden)
> vol3 -f Win10.raw windows.netstat.NetStat

NetScan: reviews network info for connections, ports, and PID (slower, may find hidden)
> vol3 -f Win10.raw windows.netscan.NetScan

FileScan: scans memory for file objects present
> vol3 -f Win10.raw windows.filescan.FileScan

HiveList: lists all available registry hives in memory
> vol3 -f Win10.raw windows.registry.hivelist.HiveList

Strings: search for string values in memory
> strings Win10.raw | grep -i copyright
>> grep = search for the following
>> 
>> -i = ingnore case

