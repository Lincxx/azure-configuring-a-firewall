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

(Observe DHCP Traffic)
1. Back in Wireshark, filter for DHCP traffic only
2. From your Windows 10 VM, attempt to issue your VM a new IP address from the command line
   - Open PowerShell as admin and run: ipconfig /renew
   - Observe the DHCP traffic appearing in WireShark

Observe DNS Traffic)
Back in Wireshark, filter for DNS traffic only
From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are
Observe the DNS traffic being show in WireShark

(Observe RDP Traffic)
Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)
Observe the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted
