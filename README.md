# ILEA-2025-Memory-Capture-Analysis

AVML (Linux)
https://github.com/microsoft/avml

Belkasoft Live Ram Capture (Win)
https://belkasoft.com/ram-capturer

Cederpelta (Mac/Linux)
https://www.brimorlabsblog.com/2019/04/live-response-collection-cedarpelta.html

FTK Imager (Win)
https://www.exterro.com/digital-forensics-software/ftk-imager

Magnet Ram Capture (Win)
https://www.magnetforensics.com/resources/magnet-ram-capture/

REMnux
https://remnux.org/

Volatility3
https://github.com/volatilityfoundation/volatility3

-----
-----
SANS Memory Forensics Cheat Sheet 3.0
https://sansorg.egnyte.com/dl/4QwNVeoj02

-----
-----
Memory Capture Workflow with Volatility3 using a REMnux Virtual Machine

Additional command arguments:
>vol3 -q -r pretty -f WIN10.mem windows.netscan.NetScan > NetScan.txt
>> (-q = run without status bar)
>> (-f = use the folling memory filescan)
>> (-r pretty = renders the text lined up in each column)
>> (>= output to file name fm-tetris.netscan.txt)
    

Windows Info: system information
vol3 -f VMram.raw windows.info.Info

PsList: Lists process IDs and parent process IDs

