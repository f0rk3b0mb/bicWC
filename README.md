
# bicWC misc challenge

credit :p3rf3ctr00t_ke

this is the writeup of the misc challange rated easy in bicWC


when the challange is started there is a download called capture.zip , its contents are a pcap file.

if you dont know pcap files a captured network packets so we are going to use wireshark. You can open the file using wireshark by typing "wireshark capture.pcap" in terminal.


once wireshark is open the first question ,

How many packets have been captured?



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-28-48.png)

the number of packets is shown at the  right bottom of the screenshot above > 1309


What is the ip address of the attacker?


here we will use the tcp filter in wireshark as shown below



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-09-44.png)

the ip is 45.15.156.72

Which city is the ip addresss based?

we will use an online iplocator tool?



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-37-57.png)


the city is amsterdam

How many dns servers sre in the pcap?

here we just us the dns filter in wireshark 



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-39-57.png)


the answer is two there is one with ip xxx.100 and xxx.101


What if the ip of the ntp server?


here we will use the ntp filter in wireshark



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-09-52.png)

the ip address as you can see above is 51.145.123.29

What machine is was transmitted to the attacker?

here will follow the tcp steam of one of the requests to the attacker as shown below  this time we will use the ip address filter <ip.addr == 45.15.156.72>




![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-45-38.png)


the machineis is a parameter of the post requests

What is the user-agent?

as you can see from the picture above the user agent is xxx

What was the mac address os the compromised machine?


we just have to double click on one of the tcp packets between the attacker and compromised machine as shown below , the mac address is on the blue line i have highlighted





![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-50-18.png)


what email address os the registrar of the ip address?


here we will conduct a whois serch on the ip address, to make work even easier we will combine it with a grep filter for the @ symbol which is used in email addresses





![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2007-53-54.png)
  
  
  
 the above challenge was rated easy ,it is also a good entry to learning to use wireshark and understanding networking
  
  
  
# bicWC mobile challenge

mobile forensics/reversing writeup


when the challenge is started there is a download of an apk file
, i am not a mobile challenge person , but it was rated easy so i gave it a go :)

first things first we decompile the apk




![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-20-48.png)

i use the flags -s -r to ensure the  dex files are left untouched this is because the smali format that apktool uses is hard to read and understarnd especially for a nood like me :)

after decompiling we get the following files



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-19-57.png)


our main focus will be the files with the extension .dex 


at this point you will need the following tools:

- jdgui
- dex2jar

the links to get the following below 

[jdgui](http://java-decompiler.github.io/)
[dex2jar](https://gitlab.com/kalilinux/packages/dex2jar)

first we decompile the .dex files using dex 2 jar and then view the jar files using jdgui as shown below



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-27-01.png)

repeat the command for all the dex files , in the end we will have  the following jar files



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-28-12.png)


you will then have to open them using jdgui, at this point i struggled to find the flag not having enough knowledge in mobile forensics , anyways when i opened the classes3-dex2jar.jar  i found the flag in the mainactivity files



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-31-16.png)


there is a base64 encoded string , we decode it an find the flag



![App Screenshot](https://github.com/p0pparaz1/bicWC/blob/main/Screenshot%20from%202023-03-01%2008-32-25.png)


although i started the challenge no expectations turns out it was easy  

GOODBYE :)
