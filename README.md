# Azure Observe SSH, DHCP, DNS, and RDP
---
In this lab we are going to observe traffic flow through various protocols 
---

(Observe SSH Traffic)
1. Log back into the windows-vm
2. Back in Wireshark, start a packet capture up
3. Filter for SSH traffic only
4. From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
5. Open PowerShell, and type: ssh labuser@<private IP address>
   - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
   - Exit the SSH connection by typing ‘exit’ and pressing [Enter]
   - 
![step2](https://github.com/user-attachments/assets/d812b99c-7494-402b-8307-6ff2c085a6a5)

![step3](https://github.com/user-attachments/assets/482f0eb6-342f-4c0e-9474-d9751b8bdca5)

![step4](https://github.com/user-attachments/assets/4fbb50d5-71e2-4ebd-a565-f61f9ef32018)

(Observe DHCP Traffic)
1. Back in Wireshark, filter for DHCP traffic only
2. From your Windows 10 VM, attempt to issue your VM a new IP address from the command line
   - Open PowerShell as admin and run: ipconfig /renew
   - Observe the DHCP traffic appearing in WireShark

**For this one I had to make a script to get to see all to the steps that DHCP makes**
**Make a dhcp.bat file and add in 'ipconfig /release' on the next line down, add 'ipconfig /renew,' and then you'll be able to see it all.**

![step6](https://github.com/user-attachments/assets/9f57e2e2-3393-4a1d-9a19-152feac0ee29)


(Observe DNS Traffic)
1. Back in Wireshark, filter for DNS traffic only
2. From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are
   - Observe the DNS traffic being show in WireShark
   
**With the DNS, we'll use the command window and do a NSLOOKUP on disney.com**
**Now look at Wireshark and you'll all the DNS traffic**

![step7](https://github.com/user-attachments/assets/c3aff392-aa06-4522-baa4-7fc1e1866623)


(Observe RDP Traffic)
1. Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)
2. Observe the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
   - Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted
  
![step8](https://github.com/user-attachments/assets/e3bbffa1-20f7-408f-adf5-ef70dc64bbb4)
