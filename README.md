# Metasploit-for-reconnaissance
# Name:DIVYA M
# Reg no : 212223040043

# Metasploit
# Metasploit for reconnaissance in pentesting

# AIM:
To get introduced to Metasploit Framework and to perform reconnaissance in pentesting .

# DESIGN STEPS:
Step 1:
Install kali linux either in partition or virtual box or in live mode

Step 2:
Investigate on the various categories of tools as follows:

Step 3:
Open terminal and try execute some kali linux commands

Find out the ip address of the attackers system

# OUTPUT:
<img width="701" height="395" alt="image" src="https://github.com/user-attachments/assets/2638c21d-f9e2-4b24-98f6-20456d851525" />

Invoke msfconsole:

# OUTPUT:
<img width="847" height="538" alt="image" src="https://github.com/user-attachments/assets/3e4e8cfd-95c3-495c-9b87-38c67f005fdb" />

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

# OUTPUT:
<img width="726" height="191" alt="image" src="https://github.com/user-attachments/assets/c55c985c-08cb-4961-826c-917e8bc64afb" />

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT  10.0.2.0/24-p1-1000

# OUTPUT:

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 10.0.2.0/24
<img width="915" height="564" alt="image" src="https://github.com/user-attachments/assets/8f5fb768-97de-4dc2-8c25-c19c9e4bff05" />


# OUTPUT:
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
# OUTPUT:

<img width="556" height="503" alt="image" src="https://github.com/user-attachments/assets/3b9c5535-dada-44d9-a7c8-58b9ec4b4d44" />

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

<img width="994" height="704" alt="image" src="https://github.com/user-attachments/assets/c6d8e102-0529-489c-8853-10e2b8b856ea" />

# OUTPUT:

The info command provides information regarding a module or platform,
<img width="991" height="705" alt="image" src="https://github.com/user-attachments/assets/fe302162-6c9f-4902-9bff-2c041fcccea6" />


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION 
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
<img width="996" height="706" alt="image" src="https://github.com/user-attachments/assets/64663552-c6af-4c8c-94fa-d1494fc35adf" />


# OUTPUT:
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
<img width="999" height="700" alt="image" src="https://github.com/user-attachments/assets/cd255fd6-682d-48fe-ae7e-f03c1299cb61" />


# OUTPUT:

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
<img width="1000" height="705" alt="image" src="https://github.com/user-attachments/assets/b82d1589-2c34-4de6-b634-b099b71ebace" />


# OUTPUT:

Use the set rhosts command to set the parameter and run the module, as follows:
<img width="992" height="460" alt="image" src="https://github.com/user-attachments/assets/a1a247fd-b7cb-4e1a-93a3-b2d7e7f2039e" />


# OUTPUT:

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
<img width="994" height="462" alt="image" src="https://github.com/user-attachments/assets/299d6c8c-df0c-4d1a-a822-62f33f6bb87d" />


# OUTPUT:

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

<img width="992" height="699" alt="image" src="https://github.com/user-attachments/assets/8ee15900-fd3b-4129-9f69-ad6af5de77c4" />

# RESULT: 
The Metasploit framework for reconnaissance is examined successfully
