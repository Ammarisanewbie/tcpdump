# Analysing Traffic with tcpdump on Linux
---
Welcome to my project about studying packet analysis with tcpdump. Here, I'll share what I've learned and the procedures and knowledge I've gathered during this hands-on practice.

### Description
This is a basic project with the purpose of learning the different commands and arguments available for tcpdump, utilising them to capture network packets and saving them in a pcap file for analysis which can be used for Wireshark.

### Software/ Tools Used
- tcpdump

### Learning Objectives
1. How tcpdump works
2. Using tcpdump to capture TCP packets
3. Analyse captured packets

### Arguments Explored
- -c
- -w
- -#
- -XX
- -tttt
- -G
- -C
- -D
- -i
- host
- port

### Installation
Tcpdump is included with several Linux distributions, but by any chance you do not have it installed, please follow the steps below to get it resolved.

1. Check whether tcpdump is installed with
  `which tcpdump`

2. Installing tcpdump with
`sudo dnf install -y tcpdump`

3. Install and upgrade any updates
`sudo apt update && upgrade`
