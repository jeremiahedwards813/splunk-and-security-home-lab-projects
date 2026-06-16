## Failed Login Summary

index=* sourcetype=WinEventLog:Security EventCode=4625
| stats count by Account_Name, host
| sort - count
