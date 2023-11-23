1. check connection :
![](../Attachemnts/Pasted%20image%2020231107152755.png)
connection established 
2. active scanning 
### [[nmap)  ###

- command:
```
sudo nmap -vvv -Pn -sCV -p0-65535 --reason -oN lame.nmap 10.10.10.3
```

| -vvv | make Nmap output detailed information about the scan |
|---:  |---: |
| -Pn | to skip the check connection and immediately scan the target port |
| -sCV | combine 2 scan types service and version detection |
| -p0-65535 | scan all ports in this range |
| --reason | include a reason output to explain why a particular port was determined |
| -oN | save the scan result in the specified text file |

- we found 4 open ports :

| Service | port | 
  |---: |---: |
  | [[ftp) |  21 | 
  | [[ssh) | 22 | 
  | [[samba) |  139 | 
  | [[samba) | 445 | 
  | [[distccd) | 3632 |



  

 






