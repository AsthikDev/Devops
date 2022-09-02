# **KL-1**
## **KL-1.2**
### 1. **Home directory**  
The home directory is where the user data for each specific user is created under the root directory. Its initial user directory will be created on that user name. It is represented by a ***`tilda (~)`*** symbol. Once the user log into the shell he will in his home directory by default.
<pre>
<b><i>Example:</i></b>
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~$ pwd  
  /home/asthik
</pre>
<img src=images\linux\Fig_1.1.jpg>

### 2. **Command & Arguments**  
Commands in linux has specific command argument or no arguments & sometimes a flag with a command. The argument provides input to the command. Flags modify the operation of a command and are sometimes called options or switch.
<pre>
<b><i>Example:</i></b>
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~$ echo $USER
  asthik
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~$ ls -l
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
* In first command ***`echo $USER`***, echo is command & $USER is argument
* In second command ***`ls -l`***, ls is command & -l is called flag

#### 2.1 **Command types**  
There are two types of commands,  
* Internal / Builtin commands
* External Commands
<pre>
<b><i>Example:</i></b>
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~$ type echo
  echo is a shell builtin
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~$ type cd
  cd is a shell builtin
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~$ type mv
  mv is /usr/bin/mv
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~$ type uptime
  uptime is /usr/bin/uptime
</pre>
In the example above,
* In first / second command ***`type echo & type cd`***, echo & cd is Internal / Builtin commands, which is defined by shell (bash)
* In third / fourth command ***`type mv & type uptime`***, mv & uptime is external commands created either through another software package or third party dependencies (currently stored under /bin directory)

<img src=images\linux\Fig_1.2.jpg>

### 3. **Basic linux commands**  
Few basic commands in Linux are given below,
* **`tree`** - List the entire contents of the directory / sub directories in tree structure (Tree binaries should be installed before using this command)
* **`pwd`** - Present working directory
* **`mkdir <foldername>`** - Make new directory from the current directory
  * **`mkdir -p <parent folder name>/<child folder name>`** - Make new directory while creating its parent directory if not created
* **`ls`** - List contents
  * **`ls -l OR ll`** - Long list contents of current directory, which also displays the files / folders properties
  * **`ls -la`** - Long list contents of current directory, which also displays the hidden files / folders properties
  * **`ls -lt OR ls -l -t`** - Long list contents of current directory, which displays in the order of files created
  * **`ls -ltr OR ls -l -t -r`** - Long list contents of current directory, which displays in the reverse order of files created
* **`pushd <folder name>`** - Remembers the current working directory before moving to the directory mentioned in the argument & it can be used as many times but it will remember the previous directory, it works efficiently in relative to the another command ***`popd`***
* **`popd`** - This command returns to the original previous directory when created with ***`pushd`*** command
* **`mv <source file / folder> <destination folder>`** - Move a source file / folder to a destination folder or to rename a file / folder
* **`cp <source file> <destination folder>`** - Copy a file from source directory to destination directory
  * **`cp -r <source folder> <destination folder>`** - Copy source directory to destination directory
* **`rm <filename>`** - Remove a file from current directory
  * **`rm -r <foldername>`** - Remove a folder from current directory
* **`cat <filename>`** - Display the contents of the file
  * **`cat > <filename>`** - Create a file with the provided filename (If file is not created) as argument & enter the contents as you give in next line **OR** Replace entire contents with the content you enter after the command (If file is already present). To exit out of session ***`press "Enter" & "Ctrl + D"`***
  * **`cat >> <filename>`** - Append the contents you enter to the last of lines of the file.To exit out of session ***`press "Enter" & "Ctrl + D"`***.
* **`touch <filename>`** - Create an empty blank file in current directory
<pre>
<b><i>Example:</i></b>
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ tree
  .

  0 directories, 0 files
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ pwd
  /home/asthik/Test
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ mkdir fol1
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ tree
  .
  └── fol1

  1 directory, 0 files
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ mkdir fol2 fol3
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol2
  └── fol3

  3 directories, 0 files
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ mkdir -p fol4/fol5
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol2
  ├── fol3
  └── fol4
      └── fol5

  5 directories, 0 files
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ ls -l
  total 16
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 12:49 fol1
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 12:49 fol2
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 12:49 fol3
  drwxrwxr-x 3 asthik asthik 4096 Aug 21 12:49 fol4
  <b><b><b><b><b>asthik@LM21</b></b></b></b></b>:~/Test$ ls -la
  total 24
  drwxrwxr-x  6 asthik asthik 4096 Aug 21 12:49 .
  drwxr-x--- 19 asthik asthik 4096 Aug 21 12:48 ..
  drwxrwxr-x  2 asthik asthik 4096 Aug 21 12:49 fol1
  drwxrwxr-x  2 asthik asthik 4096 Aug 21 12:49 fol2
  drwxrwxr-x  2 asthik asthik 4096 Aug 21 12:49 fol3
  drwxrwxr-x  3 asthik asthik 4096 Aug 21 12:49 fol4
  <b><b><b><b>asthik@LM21</b></b></b></b>:~$ pwd
  /home/asthik
  <b><b><b><b>asthik@LM21</b></b></b></b>:~$ pushd Test
  ~/Test ~
  <b><b><b><b>asthik@LM21</b></b></b></b>:~/Test$ pushd /bin
  /bin ~/Test ~
  <b><b><b><b>asthik@LM21</b></b></b></b>:/bin$ pushd /opt
  /opt /bin ~/Test ~
  <b><b><b><b>asthik@LM21</b></b></b></b>:/opt$ cd /home
  <b><b><b><b>asthik@LM21</b></b></b></b>:/home$ cd /opt
  <b><b><b><b>asthik@LM21</b></b></b></b>:/opt$ popd
  /bin ~/Test ~
  <b><b><b><b>asthik@LM21</b></b></b></b>:/bin$ popd
  ~/Test ~
  <b><b><b><b>asthik@LM21</b></b></b></b>:~/Test$ popd
  ~
  <b><b><b><b>asthik@LM21</b></b></b></b>:~$ popd
  bash: popd: directory stack empty
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ rm -r fol3 fol4
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  └── fol2

  2 directories, 0 files
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cat test.txt
  cat: test.txt: No such file or directory
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cat > test.txt
  This is first line.
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cat >> test.txt
  This is second line.
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cat test.txt
  This is first line.
  This is second line.
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cat > test.txt
  This will replace entire contents.
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cat test.txt
  This will replace entire contents.
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ touch test2.txt
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cat test2.txt
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol2
  ├── test2.txt
  └── test.txt

  2 directories, 2 files
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ mv test2.txt fol2
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol2
  │   └── test2.txt
  └── test.txt

  2 directories, 2 files
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ mkdir fol3
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ mv fol3 fol2
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol2
  │   ├── fol3
  │   └── test2.txt
  └── test.txt

  3 directories, 2 files
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cp test.txt fol2/fol3
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol2
  │   ├── fol3
  │   │   └── test.txt
  │   └── test2.txt
  └── test.txt

  3 directories, 3 files
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ mv fol2/fol3/test.txt fol2/fol3/renamed.txt
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ mv fol2 renamedfolder
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── renamedfolder
  │   ├── fol3
  │   │   └── renamed.txt
  │   └── test2.txt
  └── test.txt

  3 directories, 3 files
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ mv renamedfolder fol2
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ mkdir fol4
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cp fol4 fol2/fol3
  cp: -r not specified; omitting directory 'fol4'
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ cp -r fol4 fol2/fol3
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol2
  │   ├── fol3
  │   │   ├── fol4
  │   │   └── renamed.txt
  │   └── test2.txt
  ├── fol4
  └── test.txt

  5 directories, 3 files
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ rm fol2
  rm: cannot remove 'fol2': Is a directory
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ rm -r fol2
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  ├── fol4
  └── test.txt

  2 directories, 1 file
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ rm fol4
  rm: cannot remove 'fol4': Is a directory
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ rm test.txt
  <b><b><b>asthik@LM21</b></b></b>:~/Test$ tree
  .
  ├── fol1
  └── fol4

  2 directories, 0 files
  <b><b>asthik@LM21</b></b>:~/Test$ ls -lt
  total 8
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 16:02 fol4
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 15:48 fol1
  <b><b>asthik@LM21</b></b>:~/Test$ ls -ltr
  total 8
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 15:48 fol1
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 16:02 fol4
  <b><b>asthik@LM21</b></b>:~/Test$ ls -l -t -r
  total 8
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 15:48 fol1
  drwxrwxr-x 2 asthik asthik 4096 Aug 21 16:02 fol4
</pre>
**NOTE:** In the above example **`"."`** represents current directory & **`".."`** represents previous directory.
#### 3.1 **Path**  
There are two types of paths,  
* Absolute path  - The complete path of respective files / folders from starting directory.
* Relative path - The path of respective files / folders from the current directory  

The absolute / relative path can be used while when providing the path to certain commands such as mkdir, cd, cat, ls, etc to be executed in / for that respective directory. Such few examples is shown below.  

**Commands:**
* **`cd`** - Change directory
  * **`cd ..`** - Change to previous directory
  * **`cd OR cd ~`** - Change directory to home directory from any other directories
  * **`cd <Absolute path>`** - Change to path from starting folder to mentioned destination folder
  * **`cd <Relative path>`** - Change to path from current folder to mentioned destination folder. Note that the destination folder should be having its relative parent folder, where this command is executed.  
* **`ls -l <Absolute OR Relative path>`** - Long list contents of respective directory, which also displays the files / folders properties
* **`mkdir <Absolute OR Relative path>`** - Create directory in respective directory path.
* **`cat <Absolute OR Relative path>`** - Display contents of respective file / directory, in mentioned path
<pre>
<b><i>Example:</i></b>
<b>asthik@LM21</b>:~/Test$ tree
.
├── fol1
└── fol4

2 directories, 0 files
<b>asthik@LM21</b>:~/Test$ cd fol1
<b>asthik@LM21</b>:~/Test/fol1$ cd
<b>asthik@LM21</b>:~$ mkdir fol1/fol2
mkdir: cannot create directory ‘fol1/fol2’: No such file or directory
<b>asthik@LM21</b>:~$ mkdir /Test/fol1/fol2
mkdir: cannot create directory ‘/Test/fol1/fol2’: No such file or directory
<b>asthik@LM21</b>:~$ mkdir ./Test/fol1/fol2
<b>asthik@LM21</b>:~$ mkdir Test/fol4/fol3
<b>asthik@LM21</b>:~$ cd Test
<b>asthik@LM21</b>:~/Test$ cd ~
<b>asthik@LM21</b>:~$ cd ./Test
<b>asthik@LM21</b>:~/Test$ tree
.
├── fol1
│   └── fol2
└── fol4
    └── fol3

4 directories, 0 files
<b>asthik@LM21</b>:~/Test$ pwd
/home/asthik/Test
<b>asthik@LM21</b>:~/Test$ cat > /home/asthik/Test/fol1/Test1.txt
This is file 1.
<b>asthik@LM21</b>:~/Test$ cat > fol4/Test2.txt
This is file 2.
<b>asthik@LM21</b>:~/Test$ tree
.
├── fol1
│   ├── fol2
│   └── Test1.txt
└── fol4
    ├── fol3
    └── Test2.txt

4 directories, 2 files
<b>asthik@LM21</b>:~/Test$ ls -l /home/asthik/Test/fol4
total 8
drwxrwxr-x 2 asthik asthik 4096 Aug 23 09:27 fol3
-rw-rw-r-- 1 asthik asthik   16 Aug 23 09:30 Test2.txt
</pre>

#### 3.2 **Pagers**  
The data or content of files can also be viewed using pagers (for large file content) using ***`more`*** or ***`less`*** command.  
With the help of more command, a large file can be scrolled down page by page to view file content, similarly the less command can also be used for the same purpose.
* Also, during viewing using command - ***`more <filename>`***, by pressing, 
  * Space - Scrolls the display one screen at at time
  * b - Scrolls the display backward one screen at at time
  * Enter - Scrolls the display one line
  * / - Search text
* Also, during viewing using command - ***`less <filename>`***, by pressing, 
  * Up arrow - Scrolls up the display one line
  * Down arrow - Scrolls down the display one line
  * / - Search text  
  Press ***`q`*** to quit viewing file when using the less command