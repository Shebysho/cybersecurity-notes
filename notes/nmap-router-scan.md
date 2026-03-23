Router Nmap Scan Analysis

Date: March 23, 2026
Target: TP-LINK AC12 Router (192.168.1.1)
MAC: 00:EB:D8:0F:32:C8 (Mercusys Technologies)
Nmap Scan Results

bash
nmap -sV 192.168.1.1 -oN router_scan.txt

Output:

text
PORT    STATE SERVICE VERSION
80/tcp  open  http    TP-LINK AC12 http config  
1900/tcp open  upnp   TP-LINK router upnpd

Services Analysis

Port 80/tcp - HTTP Management Panel

    TP-LINK AC12 web configuration interface

    Attack Vector: Default credentials admin:admin

    Next: firefox http://192.168.1.1

Port 1900/tcp - UPnP/SSDP

    Universal Plug and Play service

    Risk: Unauthenticated port forwarding

    Attack Vector: UPnP abuse, SSDP amplification
