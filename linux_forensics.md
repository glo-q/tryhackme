# TryHackMe 

https://tryhackme.com/room/linuxforensics

---

## Linux Forensics

### Task 3

> In the attached VM, there is a user account named tryhackme. What is the uid of this account?

```bash
cat /etc/passwd | grep tryhackme
```

<details><summary>ANSWER (CLICK)</summary>
<p>

`1001`

</p>
</details>


> Which two users are the members of the group `audio`?

```bash
cat /etc/group | grep audio
```
<details><summary>ANSWER</summary>
<p>

`ubuntu,pulse`

</p>
</details>


> A session was started on this machine on Sat Apr 16 20:10. How long did this session last?

```bash
sudo last -f /var/log/wtmp
```
<details><summary>ANSWER</summary>
<p>

`01:32`

</p>
</details>

### Task 4 

> What is the hostname of the attached VM?

```bash
cat /etc/hostname
```
<details><summary>ANSWER</summary>
<p>

`Linux4n6`

</p>
</details>

> What is the timezone of the attached VM?

```bash
cat /etc/timezone
```
<details><summary>ANSWER</summary>
<p>

`Asia/Karachi`

</p>
</details>


> What program is listening on the address 127.0.0.1:5901?

```bash
netstat -natp | grep 127.0.0.1:5901
```
<details><summary>ANSWER</summary>
<p>

`xtigervnc`

</p>
</details>


> What is the full path of this program?

```bash
ps aux | grep Xtigervnc
```
<details><summary>ANSWER</summary>
<p>

`/usr/bin/Xtigervnc`

</p>
</details>


### Task 5

> In the bashrc file, the size of the history file is defined. What is the size of the history file that is set for the user Ubuntu in the attached machine?

```bash
cat /etc/bash.bashrc | grep history
echo $HISTFILESIZE 
```


<details><summary>ANSWER</summary>
<p>

`2000`

</p>
</details>


### Task 6
> The user tryhackme used apt-get to install a package. What was the command that was issued?

```bash
cd /home/tryhackme
sudo cat .bash_history | grep apt-get
```
<details><summary>ANSWER</summary>
<p>

`sudo apt-get install apache2`

</p>
</details>


> What was the current working directory when the command to install net-tools was issued?

```bash
cat /var/log/auth.log* |grep -i COMMAND|grep net-tools|tail
```
<details><summary>ANSWER</summary>
<p>

`/home/ubuntu`

</p>
</details>


### Task 7
> Though the machine's current hostname is the one we identified in Task 4. The machine earlier had a different hostname. What was the previous hostname of the machine?

```shell
cat /var/log/syslog* | grep "hostname changed"
```
<details><summary>ANSWER</summary>
<p>

`tryhackme`

</p>
</details>
