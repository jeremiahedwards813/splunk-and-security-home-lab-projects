
## Failed Windows Logins Detection

```spl
index=* sourcetype=WinEventLog:Security EventCode=4625
| stats count by Account_Name, host, src_ip
