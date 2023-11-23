**samba :445/tcp  open   syn-ack ttl 63 Samba smbd 3.0.20-Debian (workgroup: WORKGROUP)**

- version : Samba smdb 3.0.20 
- Run searchsploit to search the exploit code
![](../Attachemnts/Pasted%20image%2020231107185815.png)
- Script Analysis :
![](../Attachemnts/Pasted%20image%2020231107190538.png)
the key part is in def exploit :
![](../Attachemnts/Pasted%20image%2020231107191449.png)
- nohup (short for " no hang up ")  execute command to ignore the HUP (hangup) signal and therefore does not stop.
-  in linux \`\` are used to execute  a command and capture its output just like $() it seems like Samba is allowing that to happen inside the username 
- username = ``` /=`nohup [payload]`
- password = random 16 characters 
- domain = user provided domain

I use 'smbmap'  enumeration:
![](../Attachemnts/Pasted%20image%2020231107194405.png)

we have read write access to one of the shares ~/tmp 
after that i try to connect using  sbmclient but i had this error 
![](../Attachemnts/Pasted%20image%2020231107222658.png)
to fix this error i add to the command 
```
--option='client min protocol=NT1'
```
or simply add  ``` client min protocol=NT1 ```  to /etc/samba/smb.conf
![](../Attachemnts/Pasted%20image%2020231107224543.png)
the logon command refers to the act of logging in 
and i start a netcat listener :
![](../Attachemnts/Pasted%20image%2020231107230507.png)
the connection is established 
![](../Attachemnts/Pasted%20image%2020231107230548.png)
machine owned :)