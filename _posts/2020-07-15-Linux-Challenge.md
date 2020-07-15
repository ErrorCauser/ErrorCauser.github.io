---
title: "TryHackMe | Linux Challenge - Walktrough"
layout: post
---

![linuxlogo](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fhdqwalls.com%2Fwallpapers%2Flinux-tux-minimalism-4k-42.jpg&f=1&nofb=1)

Hello Guys!
Today we will discuss the Linux Challenge Walktrought Room on TryHackMe.com
This rooms purpose is to learn or improve your Linux skills.

There will be challenges that will involve you using the following commands and techniques:

    Using commands such as: ls, grep, cd, tail, head, curl, strings, tmux, find, locate, diff, tar, xxd
    Understanding cronjobs, MOTD's and system mounts
    SSH'ing to other users accounts using a password and private key
    Locating files on the system hidden in different directories
    Encoding methods (base64, hex)
    MySQL database interaction
    Using SCP to download a file
    Understanding Linux system paths and system variables
    Understanding file permissions
    Using RDP for a GUI

URL: [Linux Challenge](https://tryhackme.com/room/linuxctf)

Difficulty: Very Easy

Author: [Ben](https://tryhackme.com/p/ben)

**Task 2-1: Garry's Home Directory**

The first Task is to SSH into Garry's System. We already got the SSH Credentials. In this Case the Command would be the following:

![ssh](https://cdn.discordapp.com/attachments/723180241140318278/732925358155890748/unknown.png)

As we can see, there are a Total of **3 Files** in his Home Directory.


**Task 3: The Basics**

**Task 3-1: Flag 1**

In this Case, the Flag is in our Directory. We simply have to use the Command cat to Display it. In the File we also see the Login Credentials
for the User Bob.

![flag1](https://cdn.discordapp.com/attachments/723180241140318278/732927712041238528/unknown.png)

**Answer:** f40dc0cff080ad38a6ba9a1c2c038b2c
**Credentials:** bob:linuxrules

**Task 3-2: Flag 2**

We have the Login Credentials for Bob. We now open a SSH Session with Bob. the Second Flag is located in the /home Directory too.

![flag2](https://cdn.discordapp.com/attachments/723180241140318278/732929173387083837/unknown.png)

**Answer:** 8e255dfa51c9cce67420d2386cede596

**Task 3-3: Flag 3**

Use **ls -la** to Display all hidden files and Directorys. 

![flag3](https://cdn.discordapp.com/attachments/723180241140318278/732929921600454686/unknown.png)

**Answer:** 9daf3281745c2d75fc6e992ccfdedfcd

**Task 3-4: Flag 4**

To identify this Flag, we needed a User defined Cronjob Command. 

```$ crontab -e```

![flag4](https://cdn.discordapp.com/attachments/723180241140318278/732931331650224158/unknown.png)

**Answer:** dcd5d1dcfac0578c99b7e7a6437827f3

**Task 3-5: Flag 5**

We got the Hint to use the find Command, so the Command I used was the following: 

```$ grep -rw "flag5"```

![flag5](https://cdn.discordapp.com/attachments/723180241140318278/732933016875433994/unknown.png)

**Answer:** bd8f33216075e5ba07c9ed41261d1703


**Task 3-6: Flag 6**

This Flag requires a recursive search Command too. We got the Hint that the first two letters are "c9".

```$ cat /home/flag6.txt | grep c9```

![flag6](https://cdn.discordapp.com/attachments/723180241140318278/732934288395468821/unknown.png)

**Answer:** c9e142a1e25b24a837b98db589b08be5

**Task 3-7: Flag 7**

We got a Hint, we should check the System Processes. 

![flag7](https://cdn.discordapp.com/attachments/723180241140318278/732934996784054364/unknown.png)

**Answer:** 274adb75b337307bd57807c005ee6358

**Task 3-8: Flag 8**

The flag was zipped in a tar.gz format. I had to unzip it using the following Command:

```tar -xf flag8.tar.gz```

![flag8](https://cdn.discordapp.com/attachments/723180241140318278/732936077333233734/unknown.png)

**Answer:** 75f5edb76fe98dd5fc9f577a3f5de9bc

**Task 3-9: Flag 9**

The Hosts File is located in /etc/hosts

![flag9](https://cdn.discordapp.com/attachments/723180241140318278/732937393149182022/unknown.png)

**Answer:** dcf50ad844f9fe06339041ccc0d6e280

**Task 3-10: Flag 10**

We got told to check other Users on the System (passwd).

![flag10](https://cdn.discordapp.com/attachments/723180241140318278/732937731512074321/unknown.png)

**Answer:** 5e23deecfe3a7292970ee48ff1b6d00c

**Task 4-1: Flag 11**

This Flag was stored in the .bashrc file.

![flag11](https://cdn.discordapp.com/attachments/723180241140318278/732939553417199616/unknown.png)

**Answer:** b4ba05d85801f62c4c0d05d3a76432e0

**Task 4-2: Flag 12**

The Hint we got, tells us that this Flag is stored where MOTD Files are stored. Thoose Files Display Messages
or even Pictures on the Terminal. Thoose Files are stored under **/etc/update-m,otd.d**, we are searching for
the 00-header File.

![flag12](https://cdn.discordapp.com/attachments/723180241140318278/732941568880803910/unknown.png)

**Answer:** 01687f0c5e63382f1c9cc783ad44ff7f

**Task 4-3: Flag 13**

This Requires a **different** Command.

```$ diff flag13/script1 flag13/script2```

![flag13](https://cdn.discordapp.com/attachments/723180241140318278/732942449030332436/unknown.png)

**Answer:** 3383f3771ba86b1ed9ab7fbf8abab531

**Task 4-4: Flag 14**

Logs are mostly stored in the Directory **/var/log**.

![flag14](https://cdn.discordapp.com/attachments/723180241140318278/732943686823968808/unknown.png)

**Answer:** 71c3a8ad9752666275dadf62a93ef393

**Task 4-5: Flag 15**

Such Informations can be found in the Directory **/etc/*release** 

![flag15](https://cdn.discordapp.com/attachments/723180241140318278/732944546132131931/unknown.png)

**Answer:** a914945a4b2b5e934ae06ad6f9c6be45

**Task 4-6: Flag 16**

Mounts are usually displayed in **/mount**. This one was a bad one.

![flag16](https://cdn.discordapp.com/attachments/723180241140318278/732945386393829455/unknown.png)

**Answer:** cab4b7cae33c87794d82efa1e7f834e6

**Task 4-7: Flag 17**

We now have to log into the User **Alice**, her Password is **TryHackMe123**.
The Flag was right in the /home Directory.

![flag17](https://cdn.discordapp.com/attachments/723180241140318278/732946118970834984/unknown.png)

**Answer**: 89d7bce9d0bab49e11e194b54a601362


**Task 4-8: Flag 18**

This Flag was just a hidden File.

![flag18](https://cdn.discordapp.com/attachments/723180241140318278/732946445073645620/unknown.png)

**Answer:** c6522bb26600d30254549b6574d2cef2

**Task 4-9: Flag 19**

To read a specific Line of a File, we will need to use the following Command:

``` sed -n 2345p flag19```

![flag19](https://cdn.discordapp.com/attachments/723180241140318278/732947102425940068/unknown.png)

**Answer:** 490e69bd1bf3fc736cce9ff300653a3b

**Task 4-1: Flag 20**

This Flag requires to be Base64 Decoded. 

```$ cat flag20 | base64 --decode```

![flag20](https://cdn.discordapp.com/attachments/723180241140318278/732948101769330718/unknown.png)

**Answer:** 02b9aab8a29970db08ec77ae425f6e68

**Task 4-2: Flag 21**

We will need to inspect the File with **less** instead of **cat** since its a .php File. 
The File in inside Bob's Home Directory.

![flag21](https://cdn.discordapp.com/attachments/723180241140318278/732949056019759264/unknown.png)

**Answer:** g00djob

**Task 4-3: Flag 22**

This Flag is in Hex, we convert it into ASCII with the following Command:


```$ cat flag22 | xxd -r -p```

![flag22](https://cdn.discordapp.com/attachments/723180241140318278/732950061746749461/unknown.png)

**Answer:** 9d1ae8d569c83e03d8a8f61568a0fa7d

**Task 4-4: Flag 23** 

This Flag is located in /home/alice. it requires a text reverse Command.

```$ cat flag23|rev```

![flag23](https://cdn.discordapp.com/attachments/723180241140318278/732951150491598888/unknown.png)

**Answer:** ea52970566f4c090a7348b033852bff5

**Task 4-5: Flag 24**
In order to Display readable Strings, we need to use the following Command:
The Flag is located in the Directory **/home/garry**.

```$ strings /home/garry/flag24```

![flag24](https://cdn.discordapp.com/attachments/723180241140318278/732952286594072704/unknown.png)

**Answer:** hidd3nStr1ng

**Task 4-7: Flag 26**

To find this Flag, insert the Command below.

```find / -xdev -type f -print0 2>/dev/null | xargs -0 grep -E '^[a-z0-9]{32}$' 2>/dev/null```

![flag26](https://cdn.discordapp.com/attachments/723180241140318278/732954782779834518/unknown.png)

**Answer:** 4bceb76f490b24ed577d704c24d6955d


**Task 4-8: Flag 27**

We got Permissions to view the File.

![flag27](https://cdn.discordapp.com/attachments/723180241140318278/732955659489902643/unknown.png)

**Answer:** 6fc0c805702baebb0ecc01ae9e5a0db5

**Task 4-9: Kernel Version**

In order to get the Kernel Version, we use the Command below.

```$ uname -a```

![kernel](https://cdn.discordapp.com/attachments/723180241140318278/732956322798239764/unknown.png)

**Answer:** 4.4.0-1075-aws

**Task 4-10: Flag 29**

Follow the Steps below.

```
$ cat flag29 | tr -d ' ' >flag29_noS
$ cat flag29_noS | tr -d '/n' >flag29_noSN
$ cat flag29_noSN
```

**Answer:** fastidiisuscipitmeaei

**Task 6-1: Flag 30**

In order to get that Flag, I curled localhost.

```$ curl localhost```

![flag30](https://cdn.discordapp.com/attachments/723180241140318278/732958088306622524/unknown.png)

**Answer:** fe74bb12fe03c5d8dfc245bdd1eae13f

**Task 6-2: Flag 31**

We got MySQL Credentials. We log in into the MySQL Databse with the following Command:

```$ mysql -u root -p```

Afterwards we will type in **SHOW DATABASES;** in order to check all avaible Databases.

![flag31](https://cdn.discordapp.com/attachments/723180241140318278/732959767022272603/unknown.png)

**Answer:** 2fb1cab13bf5f4d61de3555430c917f4 

**Task 6-3: Flag 31_A**

We will now list all the table with the following Commands:

```USE database_2fb1cab13bf5f4d61de3555430c917f4```

```SHOW TABLES;```

```SELECT * FROM flags;```

![flag32](https://cdn.discordapp.com/attachments/723180241140318278/732961334135881889/unknown.png)

**Answer:** ee5954ee1d4d94d61c2f823d7b9d733c

**Task 6-4: Flag 32**

This Flag requires you to Download the .mp3 File via Filezilla and Listen to it.

**Answer:** tryhackme1337

**Task 6-5: Flag 33** 

The location to storeee your $PATH is **.profile** in Bob's Directory.

![flag33](https://cdn.discordapp.com/attachments/723180241140318278/732962417415553032/unknown.png)

**Answer:** 547b6ceee3c5b997b625de99b044f5cf

**Task 6-6: Flag 34**

In order to list the enviroment Variables, you will ned to apply the following Command:

```$ printenv```

![flag34](https://cdn.discordapp.com/attachments/723180241140318278/732962987442307172/unknown.png)

**Answer:** 7a88306309fe05070a7c5bb26a6b2def

**Task 6-7: Flag 35**

We will use the Command **getent group** for this one.

![flag35](https://cdn.discordapp.com/attachments/723180241140318278/732964717236191366/unknown.png)

**Answer:** 769afb6

**Task 6-8: Flag 36**

The Flag is located in /etc. We need to know who i allowed to read it.

```$ id```

```$ cat /etc/flag36```

![flag36](https://cdn.discordapp.com/attachments/723180241140318278/732967072728088736/unknown.png)

**Answer:** 83d233f2ffa388e5f0b053848caed1eb




