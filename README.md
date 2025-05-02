# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system

## OUTPUT:

![image](https://github.com/user-attachments/assets/d4f839cf-3e32-4a10-845f-08bdc4595593)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

systemctl start postgresql

msfdb init

Invoke msfconsole:


## OUTPUT:
![image](https://github.com/user-attachments/assets/1de79c66-3297-4c4b-9cfe-555f80963e68)

![image](https://github.com/user-attachments/assets/32b8567a-18cd-4686-897c-1d51cb3216c9)


Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

![image](https://github.com/user-attachments/assets/0d31b252-752c-497c-8e40-035ee8e72139)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

![image](https://github.com/user-attachments/assets/f228100f-8007-44f4-9810-bb17395d00c0)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l


![image](https://github.com/user-attachments/assets/f2b5d8dc-f312-4e14-99c6-8215ede31b1c)


![image](https://github.com/user-attachments/assets/210882e1-0625-41d0-b553-bc3a0378c248)
The info command provides information regarding a module or platform,

![image](https://github.com/user-attachments/assets/566cd890-3f7d-44bb-bed7-730fe5706861)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

systemctl start postgresql

msfdb init

# MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/user-attachments/assets/8345a061-1ca8-4b09-b766-a22026791e93)


Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql


![image](https://github.com/user-attachments/assets/c5ea036f-049a-4e7b-a915-85a78eeeaebe)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version


![image](https://github.com/user-attachments/assets/29b8a26d-fd05-4af5-8a97-1e03f4a6f9eb)


the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/user-attachments/assets/f65025a4-7fda-4bad-98a4-b763b49ef2b5)

 After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
 ![image](https://github.com/user-attachments/assets/0a09f7fe-0061-4321-a8cf-c89c17e155c2)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:

set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS

Set BLANK_PASSWORDS to true in case there is no password set for the root account.

set BLANK_PASSWORDS true

![image](https://github.com/user-attachments/assets/9ec69c77-4016-4456-833b-c7f1f9fb9dea)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
