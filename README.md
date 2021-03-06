# Solutions Engineer Test

Disclaimer: before doing this test, I had never installed a VM, barely used a terminal and I wasn't familiar with command lines, coding or doing everything from a command prompt. I learned everything in order to pass this test, hence made a lot of mistakes that took some time to correct (and to understand). I will detail every step of my learning and the discoveries I made, as well as how I corrected the mistakes.

First, I started by reading the [Github introduction guide](https://guides.github.com/activities/hello-world/) and followed it to create my own repository [hello-world](https://github.com/edesabarbaro/hello-world) as I had never used Github before. I read about Markdown files to understand what they were and to make sure I could format this text correctly. I explored the [Datadog Github environment](https://github.com/DataDog) to see what projects looked like, then I read the whole exercice again and started it.

Thank you for taking the time to consider my application!

You can find [at this address](https://imgur.com/a/GMviG) the full imgur album with the screenshots.

## Prerequisites - Setup the environment

<a href="https://i.imgur.com/1ObSIUb.jpg" title="Checking Vagrant installation">
<img src="https://i.imgur.com/1ObSIUb.jpg" width="400" height="217" alt="Checking Vagrant installation"></a>

**1. Checking Vagrant installation**
   - I downloaded Vagrant and VirtualBox, then checked with the cmd on Windows with `vagrant -v` if Vagrant was properly installed, and the command returned a positive answer with Vagrant 2.0.2.

<a href="https://i.imgur.com/QXXRfO5.jpg" title="Issue with Vagrant authorization">
<img src="https://i.imgur.com/QXXRfO5.jpg" width="400" height="217" alt="Issue with Vagrant authorization"></a>

**2. Issue with cmd**
   - I tried to run the VM on the cmd but it did not work: I realised the terminal on Windows was not able to do that.

<a href="https://i.imgur.com/aga7EEy.jpg" title="Booting VM on Vagrant">
<img src="https://i.imgur.com/aga7EEy.jpg" width="400" height="217" alt="Booting VM on Vagrant"></a>

**3. Booting VM on Vagrant**
   - So, I downloaded Cmder and initialized the VM with 'vagrant init hashicorp/precise64'.

<a href="https://i.imgur.com/9fhm1tX.jpg" title="VT-x error on Cmder">
<img src="https://i.imgur.com/9fhm1tX.jpg" width="400" height="217" alt="VT-x error on Cmder"></a>

**4. VT-x error on Cmder**
   - However, I ended up with a first error: `VT-x is disabled in the BIOS for all CPU modes`. So I rebooted my computer to access Bios and enable Intel Virtualization.

<a href="https://i.imgur.com/DR1LWuV.jpg" title="Timed out while waiting boot">
<img src="https://i.imgur.com/DR1LWuV.jpg" width="400" height="217" alt="Timed out while waiting boot"></a>

**5. Timed out while waiting for boot**
   - Then, I was faced with a second error `Timed out while waiting for the machine to boot`. This time, a simple restart allowed me to boot the VM properly.

<a href="https://i.imgur.com/Y276y5p.jpg" title="VM started">
<img src="https://i.imgur.com/Y276y5p.jpg" width="400" height="217" alt="VM started"></a>

**6. VM started**
   - I was finally able to start the VM with Cmder, with the name `Barbosa_default_1518895422216_47501`.

<a href="https://i.imgur.com/qdPR9lH.jpg" title="VM appears as off on VirtualBox">
<img src="https://i.imgur.com/qdPR9lH.jpg" width="400" height="217" alt="VM appears as off on VirtualBox"></a>

**7. VM appears offline on VirtualBox**
   - I was now facing a new issue: on VirtualBox, the VM appeared as Powered Off. However the name was only `Barbosa`. It gave a `file not found` error when trying to start it.

<a href="https://i.imgur.com/kvjgmCt.jpg" title="VM is duplicated">
<img src="https://i.imgur.com/kvjgmCt.jpg" width="400" height="217" alt="VM is duplicated"></a>

**8. VMs are duplicated**
   - I went to look for the missing file and realized there were two different VMs, one named `Barbosa` and the other one `Barbosa_default_1518895422216_47501`. I knew the second one was the one I had just created, so `Barbosa` should not appear in VirtualBox.

<a href="https://i.imgur.com/VR2BvdW.jpg" title="Missing file in second folder">
<img src="https://i.imgur.com/VR2BvdW.jpg" width="400" height="217" alt="Missing file in second folder"></a>

**9. Missing file found in second folder**
   - In the folder `Barbosa_default_1518895422216_47501` I was indeed able to find the missing file.

<a href="https://i.imgur.com/AoTVEze.jpg" title="Error when starting second VM">
<img src="https://i.imgur.com/AoTVEze.jpg" width="400" height="217" alt="Error when starting second VM"></a>

**10. Error when starting 2nd VM**
   - I tried to start the VM directly from the folder, but had a new error.

<a href="https://i.imgur.com/v1KAg38.jpg" title="Terminal is up">
<img src="https://i.imgur.com/v1KAg38.jpg" width="400" height="217" alt="Terminal is up"></a>

**11. The VM is running after VirtualBox restart**
   - I restarted VirtualBox, this time with admin rights. I deleted `Barbosa` and started `Barbosa_default_1518895422216_47501`, it worked!

<a href="https://i.imgur.com/6F1Eqag.jpg" title="Terminal is up">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="Terminal is up"></a>

**12. Terminal is up**
   - The terminal finally started correctly.

<a href="https://i.imgur.com/1Wv51kb.jpg" title="Changing keyboard language">
<img src="https://i.imgur.com/1Wv51kb.jpg" width="400" height="217" alt="Changing keyboard language"></a>

**13. Changing keyboard language**
   - The keyboard was set to qwerty (my own keyboard had no issue with azerty), so I entered `sudo loadkeys fr` to modify it.

<a href="https://i.imgur.com/9LTUJC6.jpg" title="Installing Datadog agent">
<img src="https://i.imgur.com/9LTUJC6.jpg" width="400" height="217" alt="Installing Datadog agent"></a>

**14. Installing Datadog agent**
   - I was then able to install the Datadog agent as requested.

<a href="https://i.imgur.com/BlhpbYG.jpg" title="Agent reporting">
<img src="https://i.imgur.com/BlhpbYG.jpg" width="400" height="217" alt="Agent reporting"></a>

**15. Agent reporting**
   - Proof on the website that the Datadog agent was finally reporting!

<a href="https://i.imgur.com/aCvy6Ta.jpg" title="Adding tags">
<img src="https://i.imgur.com/aCvy6Ta.jpg" width="400" height="217" alt="Adding tags"></a>

**16. Adding tags**
   - I added tags to the config file using `sudo nano /etc/dd-agent/datadog.conf`, then saved.

<a href="https://i.imgur.com/sfYy0EH.jpg" title="Host Map tags">
<img src="https://i.imgur.com/sfYy0EH.jpg" width="400" height="217" alt="Host Map tags"></a>

**17. Host Map tags**
   - I then checked them in the Host Map as well.

<a href="https://i.imgur.com/138JZZj.jpg" title="Installing MySQL">
<img src="https://i.imgur.com/138JZZj.jpg" width="400" height="217" alt="Installing MySQL"></a>

**18. Installing MySQL**
   - Then I proceeded to install MySQL.

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>

**00. XXXXX**
   - XXXXXXX

<a href="https://i.imgur.com/6F1Eqag.jpg" title="XXXXX">
<img src="https://i.imgur.com/6F1Eqag.jpg" width="400" height="217" alt="XXXXX"></a>
