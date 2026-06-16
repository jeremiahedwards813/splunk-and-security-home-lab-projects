

index=* sourcetype=WinEventLog:Security (EventCode=4624 OR EventCode=4625)
| stats count by Account_Name, EventCode
| sort - count
