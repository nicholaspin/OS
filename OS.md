## CMDs to run

CRON
/var/spool/cron/crontabs/  (USER LEVEL)
/etc/cron.d			(SYSTEM LEVEL)
/etc/crontab	(SYSTEM LEVEL)

crontab -u [user] file This command will load the crontab data from the specified file
crontab -l -u [user] This command will display/list user’s crontab contents
crontab -r -u [user] This Command will remove user’s crontab contents
crontab -e -u [user] This command will edit user’s crontab contents

USEFUL LINUX COMMANDS
/etc/inittab (DEFAULT RUN LEVELS/RUN LEVELS)
ss -tna (open ports and connections)
sudo lsof -i :<PORT> (gives you PID)
ps -u -p <PORT> (gives you user that its running from)
ps -ef | grep 1974 (gives you the pid)

SYSTEMD
systemctl status
systemctl list-units --type=service --all | grep -R "<>"
SYSV
service <name> status
.bash_logout
.bashrc
grep -R "" /











FINDING SIDS
Get-Localuser -Name "USERNAME" | select-object SID (SID FOR A SPECIFIC USER POWERSHELL)
Get-WmiObject win32_useraccount | Select-Object Name, SID, Domain (List all user accounts and their SIDS on the local system or a domain on powershell)



IMPORTANT THINGS TO KNOW FOR POWERSHELL
$PsHome (most precedence/profile should be checked)
$Home (second most precedence)
Get-ChildItem HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Run (Run has no sub keys, only values)
Get-item HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Run (Reads Key values, not subkeys)
Get-Filehash -Path <File> -Algorithm MD5
Get-Childitem -Force (View hidden directorys)



SysInternals Tips
TaskManager 
Autoruns



USEFUL REGISTRY KEYS
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs (Recent Files)
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList (Windows User Profiles)
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run (FOR ALL USERS ON THE MACHINE)
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles (Saved network profiles and how to decode network history)
HKU\ < SID > \Software\Microsoft\Windows\CurrentVersion\Run 
HKU\ < SID > \Software\Microsoft\Windows\CurrentVersion\RunOnce
HKLM\SYSTEM\CurrentControlSet\services
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run (RUNS EVERY TIME SPECIFIC CURRENT USER REBOOTS)






ALTERNATE DATA STREAMS (ORDER YOU SHOULD EXECUTE SEARCH)
dir /r /s | findstr "$DATA" (Gives you streams, if youre in "C:\" it gives hidden streams on whole system)
dir "<DATA STREAM>" /b /s (Command Gives you file paths for that hidden file/alternate data stream) 
more < "C:\ WHOLE FILE PATH\example:example"
