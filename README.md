

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this overview, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDP, DNS, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 22.04

<h2>High-Level Steps</h2>

- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>

                                
                                    LETS OBSERVE ICMP TRAFFIC:
![image](https://github.com/user-attachments/assets/068d3c13-2d6d-4753-a03d-b57c2c645d4c)





</p>
<p>
  Remote into your windows 10 VM and install wireshark, and then attempt to ping the UBUNTU VM (DONT FORGET THE LINUXs PRIVATE IP ADDRESS AND TO FILTER FOR ICMP TRAFFIC ONLY) Now observe ping requests and replies within wireshark.
</p>
<br />

<p>

                 INITIATE,DISABLE, AND THEN RE ENABLE NON STOP PING FROM WINDOWS 10 TO UBUNTU VM:
  ![Screenshot 2025-01-14 150658](https://github.com/user-attachments/assets/f7ccd6d1-9637-43c2-9bec-f5265e37bec8)
![image](https://github.com/user-attachments/assets/a4c86178-220a-4cfb-8e38-6f401d7c7889)
![image](https://github.com/user-attachments/assets/5c5dd7e6-ebf8-406a-b432-0d2f2db3b327)


  
</p>
<p>
Back on the azure portal open the NSG that Ubuntu VM is using and disable the incoming traffic. Observe the ICMP traffic in wireshark then Re enable traffic for group, and stop the ping activity.  
</p>
<br />

<p>

                                       OBSERVE SSH TRAFFIC
                                        
![IMG_9794](https://github.com/user-attachments/assets/ea72c396-f237-4cd2-8b25-2db204bfd3d8)

In wireshark, filter traffic to SSH only and type random commands into the linux SSH connection and watch the spam traffic in wireshark.



                                     OBSERVE DNS TRAFFIC
![image](https://github.com/user-attachments/assets/725b15e5-8dbd-4b3e-8394-d4fea5bd9b73)
In wireshark, Filter for DNS traffic only and NSLookup everyones favorite place disney and observe their IP address and observe DNS traffic.

                                    OBSERVE RDP TRAFFIC
![IMG_9798](https://github.com/user-attachments/assets/165cee2b-d928-42fc-b01d-03f67a169947)
On wireshark, filter for tcp.port==3389 and observe the immediate non stop stream of traffic.




                                    

