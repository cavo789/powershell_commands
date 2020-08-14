# Powershell commands

> Some useful commands to run in the PowerShell console

## Get list of big files

Run the command below to get a list of the largest files on your disk. Place yourself either at the root of the disk or in a sub-folder to process only that folder (recursively).

```bash
gci -r -ErrorAction SilentlyContinue | sort -descending -property length | select -first 10 fullname, @{Name="Megabytes";Expression={[Math]::round($_.length / 1MB, 2)}}
```

Result:

| FullName                              | Megabytes |
| ------------------------------------- | --------- |
| C:\...\binaries\apache\logs\error.log | 49952,22  |
| C:\...\Apps.ppkg                      | 4527,05   |
| C:\...\folder\utils.exe               | 1330,3    |
| C:\...\lib\mysqlserver.lib            | 1067,64   |
| C:\...\backup6.zip                    | 793,71    |
| C:\...\lang.psi                       | 714,23    |
| C:\...\vendor.exe                     | 700,99    |
| C:\...\MigLog.xml                     | 537,53    |
| C:\...\backup.jpa                     | 433,29    |
| C:\...\backup-cet.jpa                 | 427,76    |
