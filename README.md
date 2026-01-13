*This project has been created as part
of the 42 curriculum by jstrasse*
<h1>Born2beRoot </h1>

<h2> Description</h2>
<p>This is a 42 project. It consists on discovering the world of virtualization. Students have to install their own Linux System choosing between Debian or Rocky.</p>
<p>I chose Debian as it is more user-friendly. It's also a good choice for a personal computer and is reliable for a server. Rocky is more entreprise oriented and better for server purposes but it is a bit more complex to put in place.<br/>
I started with Rocky and was able to set it up entirely but the latest kernel version of Rocky 10 requires VirtualBox 7.1 minimum and school computers only have the 7.0 version. I asked to update it and they said it should be done soon. Nevertheless I set up another VM with Debian for the purpose of my project as I can open it at school.<br/> Throughout the change, I found that there is much more information, guides and tutorial for Debian than for Rocky. <br/><h3> Here are the main differences, Debian vs Rocky</h3> Debian we use apt to install low level packages. In Rocky we use dnf. Firewalls are enabled via UFW in Debian where as Firewalld is used on Rocky systems. APPArmor is used on Debian and SELinux on Rocky.</p> 
The main differences I found was when I was writing the monitoring script. Debian allows to see and read sudo cmds directly with the sudo users. Rocky asks the user to log in to sudo to see it. This makes the script not show the number of Sudo Commands before entering sudo. It will prompt a message with permission not allowed if not in sudo mode for this part of the script. Also some information about the cpu is located differently and some commands are different.
<h2>Instructions</h2>
Before opening the Virtual Machine, you should verify the signature. For that, you need to go in the Virtual Machine folder (It is located on my external SSD /media/jstrasse/T9/42/Born2BeRoot/), then open a terminal and type <i>shasum Born2beRoot.vdi"</i> <br/> 
This will give you the VM's signature. You can then diff it with the one in the signature.txt in the git repository. <br/>
You should also make a clone of the machine in VirtualBox before opening it. Once you open it, the signature will change. <br/>
Now you can, open the Born2beRoot VM with Virtualbox. 

<h2>Resources</h2>


<h2>Difficulties Encountered</h2>
