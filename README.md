# Solutions Engineer Test

Disclaimer: before doing this test, I had never installed a VM, barely used a terminal and I wasn't familiar with command lines, coding or doing everything from a command prompt. I learned everything in order to pass this test, hence made a lot of mistakes that took some time to correct (and to understand). I will detail every step of my learning and the discoveries I made, as well as how I corrected the mistakes.

First, I started by reading the [Github introduction guide](https://guides.github.com/activities/hello-world/) and followed it to create my own repository [hello-world](https://github.com/edesabarbaro/hello-world) as I had never used Github before. I read about Markdown files to understand what they were and to make sure I could format this text correctly. I explored the [Datadog Github environment](https://github.com/DataDog) to see what projects looked like, then I read the whole exercice again and started it.

Thank you for taking the time to consider my application!

You can find [at this address](https://imgur.com/a/ob6J1) the full imgur album with the screenshots.

## Prerequisites - Setup the environment

<a href="https://i.imgur.com/Mn7XOdG.jpg" title="Checking Vagrant installation">
<img src="https://i.imgur.com/Mn7XOdG.jpg" width="500" height="332" alt="Checking Vagrant installation"></a>

> I downloaded Vagrant and VirtualBox, then checked with the cmd on Windows with `vagrant -v` if Vagrant was properly installed, and the command returned a positive answer.

<a href="https://i.imgur.com/Ad5idoC.jpg" title="Issue with Vagrant authorization">
<img src="https://i.imgur.com/Ad5idoC.jpg" width="500" height="332" alt="Issue with Vagrant authorization"></a>

> I tried to run the VM on the cmd but it did not work: I realised the terminal on Windows was not able to do that.

<a href="https://i.imgur.com/0zlivYt.jpg" title="Booting VM on Vagrant">
<img src="https://i.imgur.com/0zlivYt.jpg" width="500" height="332" alt="Booting VM on Vagrant"></a>

> So, I downloaded Cmder and initialized the VM with 'vagrant init hashicorp/precise64'.

<a href="https://i.imgur.com/Kg3CDMF.jpg" title="VT-x error on Cmder">
<img src="https://i.imgur.com/Kg3CDMF.jpg" width="500" height="332" alt="VT-x error on Cmder"></a>

> However, I ended up with a first error: `VT-x is disabled in the BIOS for all CPU modes`. So I rebooted my computer to access Bios and enable Intel Virtualization.

<a href="https://i.imgur.com/o5FFUcH.jpg" title="Timed out while waiting boot">
<img src="https://i.imgur.com/o5FFUcH.jpg" width="500" height="332" alt="Timed out while waiting boot"></a>

> Then, I was faced with a second error `Timed out while waiting for the machine to boot`. This time, a simple restart allowed me to boot the VM properly.

<a href="https://i.imgur.com/Lrc9tFh.jpg" title="VM started">
<img src="https://i.imgur.com/Lrc9tFh.jpg" width="500" height="332" alt="VM started"></a>

> I was finally able to start the VM with Cmder, ith the name `Barbosa_default_1518895422216_47501`.

<a href="https://i.imgur.com/GQ6GXzD.jpg" title="VM appears as off on VirtualBox">
<img src="https://i.imgur.com/GQ6GXzD.jpg" width="500" height="332" alt="VM appears as off on VirtualBox"></a>

> I was now facing a new issue: on VirtualBox, the VM appeared as Powered Off. However the name was only `Barbosa`. It gave a file not found error when trying to start it.

<a href="https://i.imgur.com/qpEuv1z.jpg" title="VM is duplicated">
<img src="https://i.imgur.com/qpEuv1z.jpg" width="500" height="332" alt="VM is duplicated"></a>

> I went to look for the missing file and realized there were two different VMs, one named `Barbosa` and the other one `Barbosa_default_1518895422216_47501`. I knew the second one was the one I had just created, so `Barbosa` should not appear in VirtualBox.

<a href="https://i.imgur.com/HLYU7k1.jpg" title="Missing file in second folder">
<img src="https://i.imgur.com/HLYU7k1.jpg" width="500" height="332" alt="Missing file in second folder"></a>

> In `Barbosa_default_1518895422216_47501` I was indeed able to find the missing file.

<a href="https://i.imgur.com/uiTFLDi.jpg" title="Error when starting second VM">
<img src="https://i.imgur.com/uiTFLDi.jpg" width="500" height="332" alt="Error when starting second VM"></a>

> I tried to start the VM directly from the folder, but had a new error.

<a href="https://i.imgur.com/MNQVs1F.jpg" title="Terminal is up">
<img src="https://i.imgur.com/MNQVs1F.jpg" width="500" height="332" alt="Terminal is up"></a>

> I restarted VirtualBox, this time with admin rights. I deleted `Barbosa` and started `Barbosa_default_1518895422216_47501`, it worked!

<a href="https://i.imgur.com/QKtF6qw.jpg" title="Changing keyboard settings">
<img src="https://i.imgur.com/QKtF6qw.jpg" width="500" height="332" alt="Changing keyboard settings"></a>

> The keyboard was set to qwerty (whereas my own keyboard had no issue with azerty), so I entered sudo loadkeys fr to modify it.

<a href="https://i.imgur.com/Ad5idoC.jpg" title="XXXX">
<img src="https://i.imgur.com/Ad5idoC.jpg" width="500" height="332" alt="XXXX"></a>

> XXXXXXXXXXXXXXXXXXXXXXXX
