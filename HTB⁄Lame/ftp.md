### ftp : 21/tcp   open  ftp  syn-ack ttl 63 vsftpd 2.3.4

-  Run  ftp to  get the ftp version 
![[Pasted image 20231111200149.png]]
- version : vsFTP 2.3.4
- Run searchsploit to search the exploit code
![[Pasted image 20231111201248.png]]
![[Pasted image 20231111201956.png]]
- Script Analysis :
![[Pasted image 20231111203014.png]]
To get into the backdoor, use a 6-character username ending in ":)" and any 16-character password. This will open access to port 6200.
so I'v tried to do everything manually exactly like the screenshots bellow !
![[Pasted image 20231111213914.png]]
It seems the connection didn't go through, possibly due to a firewall blocking outbound access on port 6200. Considering this, trying an internal approach like "Prev Esc" within the system might be a viable technique. This could bypass the firewall obstruction.
- So, I've changed my focus to the [[Samba]] service. I'm exploring using this method locally for potential privilege escalations.