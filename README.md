# IP-spoofing
Details on how to spoof IP using Kali Linux

•	IP spoofing is the creation of Internet Protocol (IP) packets which have a modified source address in order to either hide the identity of the sender, to impersonate another computer system, or both.

•	Here the tool used for IP spoofing is hping3.

•	Host IP
 
![Host IP](https://user-images.githubusercontent.com/58242932/122676879-89935f80-d1fd-11eb-87dc-9737b2add845.JPG)


Victim IP

![Target IP](https://user-images.githubusercontent.com/58242932/122676888-93b55e00-d1fd-11eb-8c60-72b0df76770a.JPG)


•	Now to check the source address of the outgoing packets we will ping the gateway IP address

![Gateway](https://user-images.githubusercontent.com/58242932/122676897-9e6ff300-d1fd-11eb-9608-343df9cdfaf5.JPG)


Ping
 
![Ping before change](https://user-images.githubusercontent.com/58242932/122676906-a6c82e00-d1fd-11eb-96ea-2871a5b37c42.JPG)


•	The wireshark shows the source and destination IP address

![wireshark original ping(hl)](https://user-images.githubusercontent.com/58242932/122676972-e3942500-d1fd-11eb-8072-428aafe92607.JPG)


Packet details
 
![packet detail_1](https://user-images.githubusercontent.com/58242932/122677008-06bed480-d1fe-11eb-9d87-46ba1bbf78e5.JPG)


•	Now using the tool hping3 we will change the source address of host IP address (192.168.43.148) to Victim’s IP address (192.168.43.25). 

![hping3 command](https://user-images.githubusercontent.com/58242932/122677075-4be30680-d1fe-11eb-9e60-7d739b54e8b4.jpg)


•	Wireshark output:

![wireshark changed ping(hl)](https://user-images.githubusercontent.com/58242932/122677053-31a92880-d1fe-11eb-9c44-b6e39f24ebb0.JPG)


Packet details

![packet detail_2](https://user-images.githubusercontent.com/58242932/122677083-51405100-d1fe-11eb-9dd0-68922eb41b17.JPG)


•	Hence even if we are pinging the gateway using the host IP (192.168.43.148) the packet’s source address will not be 192.168.43.148 but the address would be 192.168.43.25 and the router 192.168.43.1 will understand that the packets are coming from the IP address 192.168.43.25 although it is sent from the Host IP (192.168.43.148).

•	Hence the IP of Host is spoofed.
