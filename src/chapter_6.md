# Change Log
# 0.11.4
This update fixes a few bugs in the reboot and reconnect process. We haven't yet diagnosed everything that has been reported, but we were able to find and fix a few issues in our own testing.
# 0.11.3
* RIM now updates itself in the background on all machines. RIM now includes the currently installed version number in the tooltip of its tray icon. This is the last update users will need to install manually, irrespective of machine configuration.
* If the target machine is rebooted, but not using RIM’s Reboot and Reconnect feature, RIM now asks the controller whether they want to reconnect to the target after the reboot. If the controller answers no, then the target won’t wait for a reconnect after the reboot.
<!-- end -->
# 0.11.2
* RIM now updates itself in the background on unattended target machines. This is the last update that you will need to install manually on your unattended targets.
* When updating before an interactive session, RIM no longer needs to go through User Account Control. This means that non-administrator users can update RIM once it has been installed for them by an administrator.
# 0.11.1
This is a bug-fix update. Please note that unattended targets still need to be updated manually by running the latest RIM installer. However, now you will be able to connect to an unattended target after the installation is done, without requiring someone to close the "Receive Help" window.
## 0.11.0
* The Reboot and Reconnect feature is now implemented. Using the new Reboot and Reconnect option on the controller’s RIM menu, you can do either a standard or emergency reboot, and automatically continue the session when the reboot is complete. RIM will also reconnect if the target machine reboots for some other reason, such as when an installer reboots the machine.
* RIM also automatically attempts to reconnect if the connection drops for any reason. This will help with unreliable Internet connections.
* When running an unattended session or using Reboot and Reconnect, you can now use RIM while the target machine is on the Windows Logon screen. Note that RIM will need to reconnect the session when the target machine transitions from the logon screen to the main desktop. This is a known limitation of the current implementation which we may address in a future update.
* RIM is now fully functional when the target user does not have administrator privileges on the target machine, as long as the Remote Incident Manager Host service is running on that machine. Note that administrator privileges are still required to install RIM updates. Also note that new versions of RIM still need to be manually installed on unattended targets. We are working on solutions to both of these problems.
<!-- end -->
# 0.10.10.0
If you've set up unattended access to one or more target machines, you can now create a shortcut to directly access any of these machines. Just press the "Create Shortcut" button under the list of unattended targets, and RIM will create a shortcut on your desktop.
# 0.10.9
RIM now works on a target machine that has no audio device. This, combined with the existing remote accessibility module, opens up access to servers and virtual machines that could previously not be accessed with a screen reader except through RDP and its very suboptimal audio output.
# 0.10.8
* If you haven’t yet pre-ordered the first year of your RIM Pro subscription, you can now easily do so using the new button on the “Provide Help” screen. We are also introducing new pricing options for adding extra controllers and concurrent channels to a RIM Pro subscription. You can add up to two additional controller users and two additional channels for $500 per year each. RIM continues to be free during the public beta, but if you pre-order your subscription now, you will have uninterrupted service when the public beta concludes on September 1.
* We are introducing Control+Shift+Backspace as an alternative hotkey for opening the RIM menu on both sides of the connection. We also still support Windows+Shift+Escape for now, but the plan is to standardize on Control+Shift+Backspace as the one hotkey for all stages of RIM.
* If you press the “Provide Help Instead” button on the “Receive Help” screen, RIM no longer sets this choice as the default until you have logged into your RIM account.
* Fixed a few JavaScript errors that occurred in rare cases.
<!-- end -->
# 0.10.7
you can now use the mouse wheel in a remote session.
# 0.10.6
Hopefully fixed all remaining issues causing the installation process to hang.
# 0.10.5
This version includes some changes under the hood. In particular, we've included updates to the installation and underlying packages to address issues causing the installation to hang.
# 0.10.4
* There is now an option on the RIM menu to send Control+Alt+Delete to the target machine.
* You can now open the RIM menu by right-clicking on the title bar of the session window. We plan to add the option of opening the RIM menu by clicking on the RIM icon at the left end of the title bar as well.
<!-- end -->
# 0.10.3
* The controller can now flip an unattended session.
* The controller can now rename an unattended target machine.
* Fixed a bug that sometimes caused the session to become unresponsive after copying to the clipboard.
* Fixed a bug that sometimes caused starting the remote accessibility module to fail with a JavaScript error.
<!-- end -->
# 0.10.2
Fixed a conflict between the RIM Client Support NVDA addon and the Dropbox addon.
# 0.10.1
* You can now pre-order the first year of your subscription to RIM Pro for $999. The link to pre-order will be available in the feedback window when you finish a remote session. Or you can follow the direct link here: Pre-order RIM Pro.
* If you have unattended target machines in your RIM account, the button to start an unattended session is now more reliably displayed on the “Provide Help” screen.
* When flipping a session, the original controller can now flip the session back, by opening the RIM menu with Windows+Shift+Escape.
<!-- end -->
