# IP-spoofing
Details on how to spoof IP using Kali Linux
•	IP spoofing is the creation of Internet Protocol (IP) packets which have a modified source address in order to either hide the identity of the sender, to impersonate another computer system, or both.
•	Here the tool used for IP spoofing is hping3.

•	Host IP
 
![image](https://user-images.githubusercontent.com/58242932/122676584-4c7a9d80-d1fc-11eb-91ca-78bd2c1dd7f0.png)


Victim IP

![image](https://user-images.githubusercontent.com/58242932/122676602-62885e00-d1fc-11eb-91fe-8a2193368263.png)


•	Now to check the source address of the outgoing packets we will ping the gateway IP address

![image](https://user-images.githubusercontent.com/58242932/122676594-58fef600-d1fc-11eb-9392-57e658fa3de1.png)


Ping
 
![image](https://user-images.githubusercontent.com/58242932/122676621-73d16a80-d1fc-11eb-92fc-fc0bfe34ae1d.png)


•	The wireshark shows the source and destination IP address

![image](https://user-images.githubusercontent.com/58242932/122676631-8186f000-d1fc-11eb-88f5-83c00c3ea199.png)


Packet details
 
![image](https://user-images.githubusercontent.com/58242932/122676642-8d72b200-d1fc-11eb-8f3b-b6e69c7eae59.png)


•	Now using the tool hping3 we will change the source address of host IP address (192.168.43.148) to Victim’s IP address (192.168.43.25). 

![image](https://user-images.githubusercontent.com/58242932/122676651-95325680-d1fc-11eb-8a39-4a0815345c33.png)


•	Wireshark output:

![image](https://user-images.githubusercontent.com/58242932/122676657-9ebbbe80-d1fc-11eb-8b4c-3f7b461cff33.png)


Packet details

![image](https://user-images.githubusercontent.com/58242932/122676665-a2e7dc00-d1fc-11eb-9a11-be51f862105c.png)


•	Hence even if we are pinging the gateway using the host IP (192.168.43.148) the packet’s source address will not be 192.168.43.148 but the address would be 192.168.43.25 and the router 192.168.43.1 will understand that the packets are coming from the IP address 192.168.43.25 although it is sent from the Host IP (192.168.43.148).
•	Hence the IP of Host is spoofed.
