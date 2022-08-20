# **KL-1**
## **KL-1.2**
<br>

### 1. **Home directory** 

The homedirectory is where the user data for each specific user is created under the root directory. Its initial user directory will be created on that user name. It is represented by a ***`tilda (~)`*** symbol.
<pre>
<b><i>Example:</i></b>
  asthik@LM21:~$ pwd  
  /home/asthik
</pre>
<br>
<p align="center">
<img src=images\linux\Fig_1.1.jpg>
</p>

### 2. **Command & Arguments**  

Commands in linux has specific command argument or no arguments & sometimes a flag with a command. The argument provides input to the command. Flags modify the operation of a command and are sometimes called options or switch.
<pre>
<b><i>Example:</i></b>
asthik@LM21:~$ echo $USER
asthik
asthik@LM21:~$ ls -l
total 32
drwxr-xr-x 2 asthik asthik 4096 Aug 20 02:25 Desktop
drwxr-xr-x 2 asthik asthik 4096 Aug 20 01:29 Documents
drwxr-xr-x 2 asthik asthik 4096 Aug 20 01:29 Downloads
drwxr-xr-x 2 asthik asthik 4096 Aug 20 01:29 Music
drwxr-xr-x 2 asthik asthik 4096 Aug 20 01:29 Pictures
drwxr-xr-x 2 asthik asthik 4096 Aug 20 01:29 Public
drwxr-xr-x 2 asthik asthik 4096 Aug 20 01:29 Templates
drwxr-xr-x 2 asthik asthik 4096 Aug 20 01:29 Videos
</pre>
In the example above,
* In first command ***`echo $USER`***, echo is command & $USER is argument.
* In second command ***`ls -l`***, ls is command & -l is called flag.
### 2.1 **Command types**  

There are two types of commands,  
* Internal / Builtin commands
* External Commands
<pre>
<b><i>Example:</i></b>
asthik@LM21:~$ type echo
echo is a shell builtin
asthik@LM21:~$ type cd
cd is a shell builtin
asthik@LM21:~$ type mv
mv is /usr/bin/mv
asthik@LM21:~$ type uptime
uptime is /usr/bin/uptime
</pre>
In the example above,
* In first / second command ***`type echo & type cd`***, echo & cd is Internal / Builtin commands, which is defined by shell (bash).
* In third / fourth command ***`type mv & type uptime`***, mv & uptime is external commands created either through another software package or third party dependencies (currenty stored under /bin directory).
<p align="center">
<img src=images\linux\Fig_1.2.jpg>
</p>