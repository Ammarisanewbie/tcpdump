# Analysing Traffic with tcpdump on Linux
Welcome to my project about studying packet analysis with tcpdump. Here, I'll share what I've learned and the procedures and knowledge I've gathered during this hands-on practice.

## Introduction
This is a basic project with the purpose of learning the different commands and arguments available for tcpdump, utilising them to capture network packets and saving them in a pcap file for analysis which can be used for Wireshark.

## Software/ Tools Used
- tcpdump

### Learning Objectives
---
1. How tcpdump works
2. Using tcpdump to capture TCP packets
3. Analyse captured packets

## Arguments Explored
- -c: *capture*
- -w: 
- -#: *adds line numbering*
- -XX
- -tttt
- -G
- -C
- -D
- -i
- host
- port

## Installation
Tcpdump is included with several Linux distributions, but by any chance you do not have it installed, please follow the steps below to get it resolved.

1. Check whether tcpdump is installed with
  `which tcpdump`

2. Installing tcpdump with
`sudo dnf install -y tcpdump`

3. Install and upgrade any updates
`sudo apt update && upgrade`

## Basic
### Open up terminal
![Picture1](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/c3087b76-58c2-4d13-8fab-752b4cb51148)

### Tcpdump Manual 
`man tcpdump`

![Picture3](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/3e899ad0-3125-405f-a6aa-954f2855f9cd)


### Capturing 10 packets
- `sudo tcpdump -c 10`

![Picture4](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/b1390383-1742-4937-ade8-11d915965487)

- `sudo tcpdump -c 10 #`: adds line and numbering for better readability

![Picture5](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/319b5b10-51d2-4472-9e8d-cec126cd0779)

- `sudo tcpdump -c 10 -#XX` 
- **XX:** displays decimal and skeys



