# Analysing Traffic with tcpdump on Linux
Welcome to my project about studying packet analysis with tcpdump. Here, I'll share what I've learned and the procedures and knowledge I've gathered during this hands-on practice.

## Introduction
This is a basic project with the purpose of learning the different commands and arguments available for tcpdump, utilising them to capture network packets and saving them in a pcap file for analysis which can be used for Wireshark.

## Software/ Tools Used
- tcpdump
- vscode

### Learning Objectives
---
1. How tcpdump works
2. Using tcpdump to capture TCP packets
3. Basic scripting

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

## 1. Basic
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

  ![Picture6](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/54dcc5b2-0ff0-4ca2-b12f-0bbde4262f58)

- Type `sudo tcpdump -c 10 -#tttt`
- **tttt:** shows in human readable format > dd:hh:mm:ss 

  ![Picture7](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/5649ac85-67a6-4cf8-a890-693f2f00f2c0)

- Type `sudo tcpdump -D`
- **-D:** shows all network interface

  ![Picture8](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/fef14c2b-ea1f-47d0-a53c-f1b311dcabb4)

- Type `sudo tcpdump -c 10 -i ens5 `
- **-i en5**: specify what you wish to display

  ![Picture9](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/58bcae1f-305e-42f7-81aa-3ad283a19f03)

## 2. Using tcpdump to capture TCP packets
### Capturing 10 packet from specified website or IP address
- In this exercise I traced packets from a host called 'skyroute66.com'
- We can see the IPv4 address of this website
- Enter `sudo tcpdump -#tttt host website/IP  -c 10`

  ![Picture10](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/4474aff6-3ada-40b8-97be-0d0974ebe655)

### Tracing of packets of a specified port
- In this exercise, I only want packets from **443** (HTTPS)
- Enter `sudo tcpdump  -#tttt -c 10 port 443`
  
  ![Picture11](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/d211fc7e-c9a8-4138-a93d-3a74d42bb488)

### Utilising operators
- Tracing packet for host and port (combining 2 and 3)
- Enter `•	sudo tcpdump -#tttt -c 10 port 443 and host skyroute66.com`

![Picture12](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/c8dba2a2-9fc0-4f4a-9991-f57ef9af9785)

### Tracing incoming/outgoing traffic
- Enter `sudo tcpdump -#tttt -c 10 src skyroute66.com`
- _src_ is interchangeable
- src: source
- dst: destination
- host: for both ways

  ![Picture13](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/e1c13eef-4942-460a-bc38-4ae0ff06b5cd)

## 3. Basic scripting
### Script to capture packets from host and write into pcap file
- Scripting is important as it automates and makes the task much easier.
- Enter the command in a text editor
  
  ![Picture14](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/de940eba-e128-44a6-8808-ff0aabbcb7ad)

- Remember to make the script executable using the code shown below

  ![Picture16](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/dcb7f89e-7702-438b-97dc-c711ca8089eb)

- Execution of script

  ![Picture17](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/9b6b4978-70f3-4327-b08e-3bc6ee25aea4)

- Creating dump files to store captured packets

  ![Picture18](https://github.com/Ammarisanewbie/tcpdump/assets/108499824/91815b44-c5ae-4653-b5ea-dde503105df6)

### Script to capture GET method packets using an expression
- This is slightly more advance, the expression can be attained from the internet.
- `sudo tcpdump -#XXtttt ‘tcp[((tcp[12:1] & 0xf0) >> 2) :4] = 0x47455420` 
  <img src="https://github.com/Ammarisanewbie/tcpdump/assets/108499824/fe02b641-b2aa-4048-8ebd-054cbc6e4d8a" height="500">

## Conclusion
I now have a deeper understanding of packet analysis with tcpdump thanks to this project. If you want to learn more about tcpdump, check out the [official documentation](https://www.tcpdump.org/manpages/tcpdump.1.html).






