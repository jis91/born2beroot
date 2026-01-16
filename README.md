<i>This project has been created as part
of the 42 curriculum by jstrasse, jstrasse@student.42lausanne.ch</i>
<h1>Born2beRoot </h1>

<h2> Description</h2>
<p>This is a 42 project. It consists on discovering the world of virtualization. Students have to install and set up their own Linux System choosing between Debian or Rocky on a Virtual Machine.</p>
<p><u>What is the purpose of a Virtual Machine ?</u> <br/>
They provide secure isolated environments for testing and development. They allow multiple and/or different operating systems running at the same time on the same hardware. <br/>
They are also used as easy backup and restoration of systems and offer legacy support for older OS.</p>
<p><u>VirtualBox or UTM ?</u><br/>
Virtualbox suits more for this project as it is intended to work cross-platform where UTM is designed primarily for MacOS. For this reason I chose to use VirtualBox.
</p>

<p><u> Rocky or Debian ? </u> <br/>
I did both but chose Debian to evaluate.<br/>
I started with Rocky and was able to set it up entirely but the latest kernel version of Rocky 10 requires VirtualBox 7.1 minimum and school computers only have the 7.0 version. I asked to update it and they said it should be done soon. Nevertheless I set up another VM with Debian for the purpose of my project as I can open it at school.<br/> Throughout the change, I found that there is much more information, guides and tutorial for Debian than for Rocky. <br/><h3> Here are the main differences between Debian and Rocky</h3> <h4> APT (Advanced Package Manager) vs DNF (Dandified YUM):</h4>
APT is a debian-system package manager where DNF is a Fedora/RHEL-system package manager. They both serve the same purpose, installing, removing, upgrading software. They are equivalent tools in different LINUX ecosystems.
<br/>
<h4>UFW (Uncomplicated Firewall) vs Firewalld</h4>
Both are firewall management tools. They control the network traffic and allow or deny connections. They protect the system against unauthorized access.<br/>
UFW is more simple and easy to use. It's better for a single-machine or a small server. <br/>
<h4>AppArmor vs SELinux</h4>
Both are Security frameworks for Linux. They implement the mandatory access control (MAC), meaning they restrict what programs can do, by confining and limiting access to files, processes and network resources.  AppArmor is more simple, easy and readable where SELinux is more complicated and preferred for servers or entreprises that need maximum security and consistency.
</p> 

<h2>Instructions</h2>
<h3><u>Before opening the Virtual Machine</u></h3><p>Before opening the Virtual Machine, you should verify the signature. For that, you need to go in the Virtual Machine folder (It is located on my external SSD /media/jstrasse/T9/42/Born2BeRoot/), then open a terminal and type <i>shasum Born2beRoot.vdi"</i> <br/> 
This will give you the VM's signature. You can then diff it with the one in the signature.txt in the git repository. <br/>
You should also make a clone of the machine in VirtualBox before opening it. Once you open it, the signature will change and other evaluators will need it. <br/>
Now you can open the Born2beRoot VM with Virtualbox.</p>

<h3><u>Opening the Virtual Machine</u></h3>
<p> Once you open the VM it will ask for the encryption password that I will fill in for you. <br/>
It will then ask to login. At first I will be the only one with a login. We will set up a user for you later on during the evaluation. A monitoring script will appear every 10 minutes showing information about the system.</p>

<h3>Things the subject requires</h3>
<ul>
<li>Check that Debian or Rocky is installed (uname -v)
</li>
<li>Check the partitionning (lsblk) <sub><i> the bonus part</i></sub></li>
<li>Check sudo policies ( /etc/sudoers.d/sudo_config)</li>
<li>SSH service <ul><li>sudo service ssh status</li><li>ssh jstrasse@localhost -p 4242 <sub><i>ssh root@localhost should fail</i></sub></li></ul></li>
<li>UFW service <ul><li>sudo ufw status <sub><i>port 4242 mandatory, other ports bonus</i></sub></li></ul></li>
<li>Check hostname (hostname)</li>
<li>Check users and groups <ul><li>sudo adduser 'your login'</li><li>sudo adduser 'yourlogin' sudo <sub><i>same for user42</i></sub></li><li>getent group sudo <sub><i>same for user42</i></sub></li></ul>
</li>
<li>Check password policy <ul><li>etc/login.defs</li><li>etc/pam.d/common-password</li></ul>
</li>
<li>Check monitoring script <ul><li>/home/jstrasse/monitoring.sh)</li><li>sudo crontab -u root -e</li></ul>
</li>
<li>Check Bonus <ul><li>Wordpress</li><li>Extra service (vsftpd and fail2ban) </li></ul></li>

</ul>




<h2>Resources</h2>
<p>Debian : www.debian.org/doc <br/>
I also found this guide useful : https://noreply.gitbook.io/born2beroot</p>
<p>Rocky : docs.rockylinux.org/guides <br/>
I also found this Git useful: https://github.com/AGolz/Born2beRoot</p>
<p>For my extra service vsftpd I used : https://wiki.debian.org/vsftpd</p>
<p> I also spent time reading stacks, forums and gits on both systems trying different stuff but my main resources are the one cited before</p>

<h2>Difficulties Encountered</h2>
<p>I did not encounter much difficulties setting up Debian as I had already done Rocky. But for Rocky I faced various challenges. First of all Rocky doesn't allow manual partitioning using text UI. I had to use the graphical interface. Thankfully it was just for the installer. The vm has no GUI. I then encountered problems with the monitoring script. Some commands are different on Rocky and permissions to see is not automatic. For example, the sudo commands cannot be seen without login into sudo. <br/>
When making the bonus part of the project I faced problems with my extra service. I chose to add vsftpd as a service. It's a simple FTP service that allows sending/receiving files. I did not have problems connecting in FTP but sending/receiving did not work at first. I realized I had to allow more ports and passive ports to send/receive files through ftp.</p>

<h2>Conclusion</h2>
<p>I had a really great time doing this project. I already knew how to install a VM before, but I hadn't done such system administration before. I also learned a lot about servers, services and file management. I had done partionning before but not an entire machine. I learned what are the implicit rules for partition names and which are mandatory. I also learned a lot of new shell commands and where to find them (like for ls, /usr/bin/ls). Thank you for reading me. </p>
