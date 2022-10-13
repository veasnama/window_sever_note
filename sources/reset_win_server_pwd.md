> # Reset Password in Window Server Administrator 

- Attach Window Server ISO into CDROM of the VM ( Winowo Server )

- Inside Installation screen click Next ->  Repair Your computer -> Troubleshooting -> Command Prompt
```
-> cd Windows\System32
-> ren Utilman.exe Utilman.exe.bak
-> ren cmd.exe Utilman.exe 
-> shutdownn -r -t 0
-> net users Administrator ChangemeVeasna#*1206
before reboot force VMWare to boot into CDROM
-> shutdown -r -t 0
-> ren Utilman.exe cmd.exe 
-> ren Utilman.exe.bk Utilman.exe 
-> shutdown -r -t 0
```
