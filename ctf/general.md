---
title: General tools
layout: article
keywords: ctf_tools
summary: "This is a list of useful code tidbits I have found useful during my learning."
permalink: /ctf_tools_general/
tags: [ctf]
---

#### This page is a list of tools and resources I have come across and use regularly when taking part in CTFs. It will serve as a reference for myself when I forget things and hopefully help others to discover.

[Rawsec's Cybersecurity Inventory](https://inventory.rawsec.ml/tools.html) has many more tools to show than here!

## [NCAT](https://linuxtechlab.com/nc-command-ncat-for-beginners/)
NC command is for performing maintenance/diagnosis tasks related to network . It can perform operations like read,write or data redirections over the network, similar to how you can use cat command to manipulate files on Linux system. Nc command can be used as a utility to scan ports, monitoring or can also act as a basic TCP proxy.

Command
connects to IP 10.10.10.100 on port 80
```
$ nc 10.10.10.100 80
```
-----------------------------

## [telnet](https://www.computerhope.com/unix/utelnet.htm)
The telnet command is used for interactive communication with another host using the TELNET protocol. It begins in command mode, where it prints a telnet command prompt ("telnet>").

-----------------------------

## [GNU debugger](https://www.geeksforgeeks.org/gdb-step-by-step-introduction/s)
GDB offers extensive facilities for tracing and altering the execution of computer programs. The user can monitor and modify the values of programs' internal variables, and even call functions independently of the program's normal behavior. (alternatively [gdb-peda](https://github.com/longld/peda) for nicer interface)

------------------------------

## [getfattr](https://linux.die.net/man/1/getfattr)
Get extended attributes of filesystem objects such as hidden files

-------------------------------

## [Wireshark](https://www.wireshark.org/)
Wireshark is the world’s foremost and widely-used network protocol analyzer. It lets you see what’s happening on your network at a microscopic level and is the standard. Useful if we need to analyze captured data packets.

--------------------------------

## Strings
A command that lists the text present in a binary file

Command
```
strings filename
```

--------------------------------

## [PostBin](https://postb.in/)
Use PostBin to collect all requests to a special URL which you can use to test your API Clients or your WebHooks. Inspect your bin visually on this website, or use our API to programmatically test your libraries, clients, projects, SaaS or websites.

--------------------------------

## [nmap](https://nmap.org/)
Nmap is a free and open-source network scanner, used to discover hosts and services on a computer network by sending packets and analyzing the responses. Nmap provides a number of features for probing computer networks, including host discovery and service and operating system detection.
It also has a GUI application called zenmap.

--------------------------------

## [Metasploit](https://www.metasploit.com/)
The Metasploit Project is a computer security project that provides information about security vulnerabilities and aids in penetration testing and IDS signature development.
It has a database of exploits in Postgresql that can be executed to gain access to vulnerable machines or networks.

---------------------------------

## [DirBuster](https://tools.kali.org/web-applications/dirbuster)
DirBuster is a multi threaded java application designed to brute force directories and files names on web/application servers.
