## SSH Exploititng
 - ### **SSH** *stands for secure shell that allows to gain computer shell across the network*
 - It use port 22
 - If you went to ssh in your Linux first download `openssh-service`
 ```shell
sudo apt install openssh-service
 ```
 - To start ur ssh simply in your terminal type
 ``` shell
 sudo systemctl start ssh | service ssh start
 ```
## SSH Login
<hr>


 - *There are two ways of  autentication  method to got*
 > # Id RSA
 > It use private  and public key to connect the shell
 > To generate private and pulic key on your computer
 ``` shell
 sudo ssh-keygen
 ```
 >  *This command generate private and public key name in your .ssh directory named **id_rsa** and **Id_rsa.pub** respectivily*
> If u have private key you able to login on your remote machine
``` shell
ssh -l id_rsa@ip_addres(of remote computer)
```
> - When we generate private and public idrsa it ask password (optional)
> - when we going to login with ssh it maybe required
> - To Brute force password using IdRSA we use `ssh2john`
> - This script help you find the hashed password
>
># Using Username and password
> - This method is only using password and username of remote shell.
``` shell
ssh username@ip_addr
```
> - Example ``` ssh hanter@129.168.2.12 ```
> - and fill your password after hited on Enter

# Exploits
- There are alot of way to Exploit /  Bruteforce the ssh
- In this note we use Hydra and Metasploit to connect / Brute force username and password
## using hydra
- **Hydra is one of the most poular tool to bruteforce the online passwods**
- *hydar use usernaem and password to brute force the login*
- you need to preoare password and username list
- ### ✔ To be fast instead of making username list first cheek or identify the username or use `enum4linux` tool to enumrate the username of machine
``` shell
hydra -l username.txt -p password.txt ssh://127.0.0.1
```
- Hydra not only use for shh it also use ftp server to crack password
## using Metasploit
> - Using Metasploit frame work it we can bruteforce the  password
> - star the metasploit Frame work using command ```msfconsole```
> - And search auxiliary
``` shell
search auxiliary/scanner/ssh/ssh_login
```
> - And use it by using `use` command
### Requirements
- set rhost = remote machine ip
``` shell
set RHOST 127.0.0.1
```
- set username   = Username of the machine using wordlistt
``` shell
set user_file
```
- set password file
``` shell
set pass_file
```
- And Finally Run/Exploit
``` shell
exploit
```
