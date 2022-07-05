# TODO: our goal is to set up openssh server on any kind of window serer 
## so that we can login from other client whether it's a linux or macs or window machine . sound pretty interesting right 

- Open PowerShell as an Administrator
- Past the following command to install OpenSSH Server 
```
Add-WindowsCapability -Online -Name OpenSSH.Server
```
- Install OpenSSH Client:
```
Add-WindowsCapability -Online -Name OpenSSH.Client
```
---
 - start-process notepad C:\Programdata\ssh\sshd_configstart-process notepad C:\Programdata\ssh\sshd_config

- Configure the Firewall

- Go to -> Server Manager -> Windows Defender Firewall with Advanced Security from the drop down list

- Click on Inbound rules Select port from the list of options 
- then check TCP and enter the port 22 in the Specific local ports: seciton 

- First, start the OpenSSH server by entering the following command in your PowerShell terminal.
- Check ssh server status 
```
Get-Service -Name *ssh*
```
- As you can see, both services are in a Stopped state and not added to the automatic startup list. To start services and configure autostart for them, run the following commands:

```
Start-Service sshd

Set-Service -Name sshd -StartupType 'Automatic'
```
- Logout of RDP session 
- Then, initiate an SSH connection from your local computer to the server using the following command
```
ssh -l Administrator SERVER-IP
```
- Replace Administrator with your target username and SERVER-IP with your actual Vultr Windows server address

- Congratulations, you have successfully installed OpenSSH on a Windows Server. To fine-tune your SSH configuration file
