# Working within a Session
## Things to Know before you Begin
A few things will happen immediately after the connection is established.
* The remote control window for the session will appear.
* You will be informed about the status of the running screen reader, or lack thereof, on the client's machine.
* If the client is running a screen reader, a toast notification informing the user that the remote session has begun will provide instant confirmation that the user's system audio is working.
* Last but not least, all keyboard and mouse input will immediately be directed to the target computer. To direct control back to your machine, do either of the following:
    * press Control+Shift+Backspace.
    * right click the RIM window's title bar.
    * left click the RIM icon.
<!-- end -->
## Remote Control Zone
At this point, you're all set to perform whatever tasks need doing on the client side. Should you need to switch back to controlling your own machine, bring up the RIM menu, then select the "Minimize session" option. You will be taken back to your machine until you switch back into the session window. When you go back into the session window, keyboard control will once again be directed to the client computer.  
Once you're done, either the controller or the target can go into the RIM menu and choose the "End Session" option. When the session ends, the target machine will get a toast notification informing them of this. At the same time, a feedback window will appear on the controller asking how the session went.
## The RIM Menu
As mentioned earlier, accessing the RIM menu directs you back to your machine. There are a number of options in this menu. They include:
* Minimize Session: brings control back to your machine as described above
* Flip Session: Allows your client to remote control your machine and hear its audio. As the original controller, you can flip the session back by selecting this option a second time.
* Start/stop Voice Conversation: Allows you to toggle the voice chat on or off for your session.
    * Note that this option is unavailable in unattended sessions as they do not support voice chat.
* Start Remote Accessibility: This option appears when no screen reader is running on the remote computer. This will enable speech on your end, but the client will not need to worry about hearing speech.
* Send Control+Alt+Delete: Sends this keystroke to the remote machine.
* Request Unattended Access: Allows you to send a request for unattended access to the client computer. This is useful if you are a sysadmin and need to perform routine maintenance, or even for something as simple as controlling your home machine while on the go.
* View Connection Details: Provides a detailed lowdown on your connection
* End Session: Terminates the session.
    * Remember that this option is available to both sides of the session.
## File Transfers
File transfers are quick and easy, as you can literally copy/paste across the session.
1. Bring up the RIM menu, and click on "Minimize Session." Control will be directed back to your computer.
1. Select the file(s) and/or folder(s) you want to transfer using your file manager of choice. It doesn't matter if this is Windows Explorer, or a third party solution such as Total Commander.
1. Copy the selected contents to the clipboard in the usual way.
1. Switch back to the remote session, and locate the folder on the target machine where you wish to paste the content.
1. Last but not least, paste as you normally would.
<!-- end -->
And just like that, the content will appear on their machine momentarily! Note that the transfer time will depend entirely on the size of the content being sent as well as your network speed.
## Remote Accessibility Module
Whether you're assisting a user who doesn't use a screen reader, or you're diagnosing an issue with a malfunctioning screen reader, RIM is fully prepared to come to your aid. The remote accessibility module consists of two components:
* An addon for the [NVDA screen reader](https://nvaccess.org) that enables the screen reader to receive output from the remote computer
* A self-contained, portable version of NVDA that runs on the client's machine only when called upon by initiating the remote accessibility on the controller side. This version of NVDA is tweaked so as to not get in the client's way, as it does not speak. Instead, it pipes the output through to the running copy of NVDA on the controller side. This way, you can accessibly assist a client without them having to install or even download a screen reader.
### Setup Procedure
For first-time initialization of the accessibility module, here is what you will need to do:
1. Bring up the RIM menu.
1. Select the "Start Remote Accessibility" option.
1. You will be asked to install an addon that will allow your copy of NVDA to communicate with the remote computer during the session. Accept the installation prompts, and wait for NVDA to restart.
1. By now, the remote accessibility module will be fully initialized, and you will hear speech output as you control the remote computer.
<!-- end -->
If you need to stop the remote accessibility module on the remote machine, simply press insert+q as you normally would to quit NVDA. The RIM version of NVDA will not prompt you before quitting.
## Requesting Unattended Access
During a one-off remote control session, you may request unattended access to the remote machine if you are the controller. This will allow you to connect to this remote computer without the user having to start RIM, enter the keyword, or even be near the computer. This is useful if you are a sysadmin performing routine maintenance on computers in your workgroup. You may also want to allow this for your home computer should you need to access it from someplace else.  
In order to configure unattended access:
1. While in an interactive session, bring up the RIM menu.
1. Select "Request Unattended Access."
1. You will be asked to give this machine a name. Enter a personal name for the machine, or if applicable, the machine ID as it appears in your workgroup.
1. Press enter.
1. On the client machine, a dialogue pops up asking the user if they're fine with their computer being set up for unattended access. If they answer yes, then you will get a prompt informing you that unattended access has been approved.
<!-- end -->

Now with that out of the way, here is how we will start an unattended session.
1. Start RIM in controller mode.
1. Rather than entering a keyword, locate and activate the"Start an unattended session instead" button.
3. When you click this, a list of machines will appear. Choose the one you want, then hit enter.
<!-- end -->
That's it! You are now connected and will be dropped into the remote control zone.  
Please note: Voice conversations are not supported during unattended sessions.
### Creating a Shortcut for an Unattended Session
For extra convenience, you can create desktop shortcuts that allow you to automatically launch unattended sessions. In order to do this:
1. Access the list of unattended computers, and select the one you want to create a shortcut for.
1. Click on the "Create Shortcut" button.
1. A shortcut will be automatically added to your desktop.
<!-- end -->
Now, when you activate this shortcut, you will automatically land in the remote session.
#### More Ways to use Unattended Session Shortcuts
Unattended session shortcuts, like any other shortcuts, can have global hotkeys associated with them. This can be extremely useful if you are a maintenance tech managing multiple computers in a workgroup. For example, if your workgroup consists of 6 computers that you perform routine maintenance on, you could configure Alt+Control+1 through 6 as hotkeys for each respective machine. This ought to greatly speed up your workflow.  
In addition, you can call up an unattended session via the run box if you copy the shortcut into your user directory. Once you've copied the shortcut, you may start an unattended session by typing your-session-name.url in the run box.
### Renaming an Unattended Computer
If you wish to rename an unattended computer:
1. Navigate to the computer you wish to rename.
1. Click on the "Rename" button.
1. Give the machine a new name, then press enter.
<!-- end -->
Note that your session shortcuts will continue to work even after renaming unattended machines.
### Revoking Unattended Access
If you no longer want your machine to be controlled unattended, you can revoke the controller's access. You do not need to be in a session in order to do this.
1. Access the Remote Incident Manager icon in your system tray.
    1. If using the keyboard, press windows+b, then space, then left or right arrow until you find the icon.
1. Right click this icon, or press the applications or shift+f10 key.
1. Select the "Revoke Unattended Access" option.
1. You will arrive at a list of computers, select the one you want to revoke.
1. You will be asked if you wish to revoke the machine; answer yes.
<!-- end -->
That's it! The controller will receive a message stating that this machine is no longer available for unattended access. Should they need unattended access again, they can reinitiate the procedure to request permission for unattended access as described above.