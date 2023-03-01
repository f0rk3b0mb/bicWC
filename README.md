
# bicWC misc challange

this is the writeup of the misc challange rated easy in bicWC


when the challange is started there is a download called capture.zip , its contents are a pcap file.

if you dont know pcap files a captured network packets so we are going to use wireshark. You can open the file using wireshark by typing <wireshark capture.pcap> in terminal.


once wireshark is open the first question ,

How many packets have been captured?


## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-28-48.png)

the number of packets is shown at the  right bottom of the screenshot above > 1309


What is the ip address of the attacker?


here we will use the tcp filter in wireshark as shown below

## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-09-44.png)

the ip is 45.15.156.72

Which city is the ip addresss based?

we will use an online iplocator tool?

## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-37-57.png)


the city is amsterdam

How many dns servers sre in the pcap?

here we just us the dns filter in wireshark 

## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-39-57.png)


the answer is two there is one with ip xxx.100 and xxx.101


What if the ip of the ntp server?


here we will use the ntp filter in wireshark

## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-09-52.png)

the ip address as you can see above is 51.145.123.29

What machine is was transmitted to the attacker?

here will follow the tcp steam of one of the requests to the attacker as shown below  this time we will use the ip address filter <ip.addr == 45.15.156.72>


## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-45-38.png)


the machineis is a parameter of the post requests

What is the user-agent?

as you can see from the picture above the user agent is xxx

What was the mac address os the compromised machine?


we just have to double click on one of the tcp packets between the attacker and compromised machine as shown below , the mac address is on the blue line i have highlighted



## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-50-18.png)


what email address os the registrar of the ip address?


here we will conduct a whois serch on the ip address, to make work even easier we will combine it with a grep filter for the @ symbol which is used in email addresses



## Screenshots

![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-53-54.png)
  
  
  
 the above challenge was rated easy ,it is also a good entry to learning to use wireshark and understanding networking
  
  GOODBYE:)
