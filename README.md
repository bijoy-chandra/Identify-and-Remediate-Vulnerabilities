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

## Steps to Reproduce

### FTP Backdoor (vsftpd)
Exploitation Details:
Module Used: exploit/unix/ftp/vsftpd_234_backdoor
Steps:
- Set target IP (RHOSTS) and port.
- Run exploit to access a backdoor shell.

![image](https://github.com/user-attachments/assets/ac76dde2-c328-4f6f-a043-42296e768b17)

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

Here we can see, two sessions has successfully created....!!!

### Outdated SSH version
The process is same like the previous one.
Module Used: auxiliary/scanner/ssh/ssh_login
Steps:
- set RHOST (VM IP address)
- set USER_FILE "Username file location"
- set PASS_FILE "Password file location"

![image](https://github.com/user-attachments/assets/3cffafe0-c023-4e80-beb9-38086223897b)

### Samba Unauthenticated Access
Module Used: auxiliary/scanner/ssh/ssh_login
Steps:
- set RHOST (VM IP address)
- Execute the exploit to open a remote shell via Samba misconfiguration.

![image](https://github.com/user-attachments/assets/be1303d3-5c8b-48e3-ab5c-f0a671ea4b01)

### Bindshell Backdoor (Metasploitable root shell)

![image](https://github.com/user-attachments/assets/11345c83-8e97-48a5-8ded-d23e1d0bbef6)




