# Frequently Asked Questions
Here are answers to some common questions concerning RIM.
## Compatibility
### What Platform(s) are supported?
The initial release of the client is only going to target Windows, but Mac and other devices are definitely on our roadmap. Windows is by and large the easiest operating system to work with when developing a remote access infrastructure, so while it is entirely possible to support RIM on more platforms, the process of implementing support for said platforms may be more involved.

The enterprise server supports a wide range of Linux flavors as well as Windows.
### Our company is still using Windows 7. Will RIM work under this configuration?
Yes, RIM supports Windows 7.
## General Session Troubleshooting
### I'm controlling a Windows Server or cloud-based virtual machine with a screen-reader installed, and do not hear any sound. What's going on?
In order for RIM to provide sound, audio drivers do need to be active. Windows Server installations generally don't activate audio services due to the fact that there's really no practical reason to do so. Unfortunately for us this means that there's a little more advanced prep needed to get sound. Not to worry, however, as RIM can fill in despite the lack of sound.  
1. Use the quit command of whichever screen reader is running on the server. Insert+Q followed by enter in NVDA's case, insert+f4 followed by enter for JAWS. You will get confirmation that the screen reader is unloaded when RIM informs you that no screen reader is running on the remote host.
1. Switch on the Remote Accessibility Module.
1. Now that you have speech, download a utility that will give your server a soundcard. One such utility is [Virtual Audio Cable,](https://vac.muzychenko.net/en/) which is free for personal use.
1. Provided the installation was successful, you should now have working sound on the server. You can test this by reloading your screen reader of choice. If all goes well, you should hear it start up and begin talking.
<!-- end -->
## Pricing and Payments
### So, getting help from a person over RIM is totally free, right?
You bet! The subscriptions and/or one-off payments are for individuals and organizations seeking to offer remote assistance. No need to worry about getting a subscription if you're the person receiving help.
### I don't really do remote assistance regularly, but I may be helping a friend or family member on occasion. Are there any options that don't involve a subscription?
Certainly! We do accommodate as many use cases as we can.
* Anyone can assist a user over RIM for free for up to 30 minutes a day. So if you need to help someone install some software, fix a problem real quick, or send over a few files, we've got you covered.
* There are, of course, going to be situations where a particular issue requires a little more time. Or maybe you're assisting someone learning a new piece of software and might be connecting on and off over the next few days. That's where our day passes come in. You can get a single day pass, a straight three day pass, or a discounted pack of three day passes that need not be used consecutively.
### How do day passes work? Does the clock start immediately upon payment, or on the day I initiate the session?
Day passes only begin when the controller initiates the session. So if the target's machine fails on them requiring a trip to the shop and a same-day turnaround is not possible, you can simply hold off until the machine is back in good shape and your day pass will still be waiting for you. Similarly, the day pass three-pack does not have to be used in three straight days. You may use one day tomorrow, and the remaining days a week from now.
### I hold an active one-to-one or one-to-three subscription. Would I still be able to assist a user outside the group for up to 30 minutes?
Yes! Your 30 minute daily allotment is still present for any machine outside of your subscription.
### I have a one-to-one subscription, and the target computer underwent a hardware upgrade. Will Rim count this as a machine switch?
Only if RIM needs to be reinstalled. So, while a hard drive upgrade or any other situation requiring a Windows reinstallation would be considered a machine switch, upgrading the ram would not.
### Our company bought the pro subscription, but we have two techs - one that does help-desk during the day, and a system maintenance tech that works in the evening. Would we be able to assign the evening sysadmin a controller seat?
Definitely. We offer an extra controller seat for $50 a month - $500 a year - to accompany the pro plan if needed. While the two controllers can't have two simultaneous sessions going on at once, this will make it easier for two controllers at two different workstations or offices to provide remote support.
## Security
### Are RIM sessions encrypted?
Yes. All sessions, whether they be direct peer-to-peer connections or connections using a relay fallback, are encrypted end to end using Datagram Transport Layer Security (DTLS).
### Do any ports need to be opened on the target or controller?
No and no.
### What connections would need to be allowed on a network in order for RIM to function?
When utilizing the public cloud, an https connection to <https://getrim.app> is required. The enterprise server for on-premises or VPC deployments listens on the standard https port (443). Port 80 needs to be open as well, though its only purpose is to facilitate https redirect.
### What background processes does RIM run, and are they light on system resources?
*rim-host-service.exe: target process
    * This is an always-on background process that runs by default as long as RIM is installed.
    * It is very light on system resources
    * It runs with maximum privileges for the purpose of elevating RIM when needed, I.E. when user account control or a similar secure screen appears during a session.
    * It downloads some components of RIM in the background so as to reduce installation time and file size.
    * It does not phone home for any other purpose
* Remote Incident Manager.exe: main executable
    * This runs continuously on machines that have been configured for unattended access. Its purpose is to listen for and initiate unattended access connections requested by the controller.
    * Still fairly light on system resources
    * Phones home only with an anonymous machine ID. No personally identifiable information is ever transferred.
    * Can be shut down via the icon in the system tray for disabling unattended access. A controller deleting a machine from the unattended access group has the same result
<!-- end -->
## Remote Accessibility Module
### Is there anything the target machine needs to configure for first-time use of the Remote Accessibility Module?
Not at all! There are no dialogue boxes or anything of the sort. In fact, the self-contained copy of NVDA that the target machine will run does not speak, so the target will not even have to concern themselves with it.
### Does the Remote Accessibility Module work on secure screens such as User Account Control?
Yes! Since the RIM host runs with elevated privileges, this allows us to leverage the Remote Accessibility Module for secure screens. Gone are the days of getting trapped in a user account control dialogue in the middle of a program installation!
### Will the Remote Accessibility Module run on a portable copy of NVDA?
Yes, and this includes secure screens since the RIM host process takes care of elevation.
### Will the Remote Accessibility Module run on the Windows Store version of NVDA?
This is not possible due to the Windows Store version of NVDA not allowing the use of addons. You'll have to either use a portable version of NVDA, or have your IT install the standard version of NVDA on your machine.
### Will my NVDA addons transfer over to this version of NVDA?
Not automatically, and this is generally not advisable anyway. The NVDA included in the accessibility module is designed to be a lightweight, trimmed down, secure solution to provide speech in an environment that otherwise wouldn't have it any other way. That said, if you are using an application for which an NVDA addon is the only way it would be accessible, then you can install that addon individually, though at this point we lack a mechanism to flush the addons directory of all user-generated content upon closing the RIM session. It's worth noting that this version of NVDA contains an addon to communicate with the RIM session, which should not be removed.
## Unattended Sessions
### Are voice conversations supported during unattended sessions?
No.
### If I delete an unattended machine from my controller account, will it automatically revoke permission on the target?
Yes. Once an unattended target is removed, the change will be effective immediately. If the target machine is powered down or otherwise not connected to the internet, the change will be effective as soon as an internet connection is established on their machine.
### The target machine rebooted after installing updates and drivers, and it requires a password to log in. How does the session continue from here?
AS of now, the RIM host service does not start pre-login. This is slated for a future update. If your maintenance requires a reboot midway through, the best thing to do would be to advise the user of this so that they will be around to log back in. Once logged in, you will be able to reconnect and finish your session.
### I have multiple machines playing the part of the controller. Will the list of machines set up for unattended access populate across all machines?
Yes. The list of machines configured for unattended access is stored within your account, so it will populate automatically.
