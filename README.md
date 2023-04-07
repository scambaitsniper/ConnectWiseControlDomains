The threat actors who are setting up these servers are working in the industry of Malware as a service (MAAS). 

TTPs:
Using Apache Servers, linux and windows vms in the cloud, paired with open ssh access. 
Most of the servers running apache are vulnerable. 

To understand how this malware works, we need to see the control panel first. 
![image](https://user-images.githubusercontent.com/126899048/230537495-db6c0e53-c6cb-4102-8cc6-c6d8f640379d.png)
![image](https://user-images.githubusercontent.com/126899048/230537527-e3931a0c-91e9-4ea1-99b0-f6cdbe6e46fc.png)
Most of the control panels will allow the attacker to create an invite only code. To download the malware and keep researchers out, they require a 6 digit password which is generated on demand.

When the victim is instructed to navigate over, they're usually greeted with the Secure Code screen, which prompts them to ask the attacker for the download password. 
![image](https://user-images.githubusercontent.com/126899048/230539557-fa9373fa-79f9-4628-b682-0a807afd9aad.png)
![image](https://user-images.githubusercontent.com/126899048/230539665-b1ab3621-7ebc-4114-9539-4fc1ce7298f0.png)
When a victim visits the page, the server starts executing javascript to determine the operating system.
![image](https://user-images.githubusercontent.com/126899048/230539807-482b449a-cf47-4e07-9264-213252aa0a00.png)
The script keeps executing as long as the victim remains on the page. 
![image](https://user-images.githubusercontent.com/126899048/230539867-6f88c652-758e-4dd4-a64a-12df5f51a49c.png)
This shows the maturity of the threat actors, because if you visit this page from a linux box or phone you will not get the exe. 


To download the "client", you must have some indication that the TA is engaging a victim and that the server is hosting the malware for download.
To retrieve the .exe you must add https before the IP (this will give you cert error bc it was issued for domains and not ip).
Then append /Bin/ConnectWise.Client.exe to the end of the IP. ex https://80.241.218.128/Bin/ConnectWise.Client.exe

Depending on which ports are open, you might have to add port 2000 or similar before /bin..
![image](https://user-images.githubusercontent.com/126899048/230540464-2ccea94b-7730-4e70-9c18-e02dbe40fcc8.png)
I have also found that they have RDP open more often than not.

Additional observation: most of servers are on Russian IP ranges, meaning the servers would be harder to take down. Shows maturity of threat actors.
