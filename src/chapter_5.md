# Frequently Asked Questions
Here are answers to some common questions concerning RIM.
## Compatibility
### What Platform(s) are supported?
The initial release of the client is only going to target Windows, but Mac and other devices are definitely on our roadmap. Windows is by and large the easiest operating system to work with when developing a remote access infrastructure, so while it is entirely possible to support RIM on more platforms, the process of implementing support for said platforms may be more involved.

The enterprise server supports a wide range of Linux flavors as well as Windows desktop and server operating systems.
### Our company is still using Windows 7. Will RIM work under this configuration?
Yes, RIM supports Windows 7.
## General Session Troubleshooting
### I'm controlling a Windows Server or cloud-based virtual machine with a screen reader installed, and do not hear any sound. What's going on?
Please ensure RIM version 0.10.9 or later is installed on both the target and controller, as this issue has been addressed.
## Pricing and Payments
### So, getting help from a person over RIM is totally free, right?
You bet! The subscriptions and/or one-off payments are for individuals and organizations seeking to offer remote assistance. No need to worry about getting a subscription if you're the person receiving help. In fact, you do not even have to set up an account if you are merely receiving help.
### I don't really do remote assistance regularly, but I may be helping a friend or family member on occasion. Are there any options that don't involve a subscription?
Certainly! We do accommodate as many use cases as we can.
* Anyone can assist a user over RIM for free for up to 30 minutes a day. So if you need to help someone install some software, fix a problem real quick, or send over a few files, we've got you covered.
* There are, of course, going to be situations where a particular issue requires a little more time. Or maybe you're assisting someone learning a new piece of software and might be connecting on and off over the next few days. That's where our day passes and incident passes come in.
    * Incident passes allow you to connect to a single target as many times as is needed over a 24 hour period.
    * Day passes allow you to connect to multiple targets over a 24 hour period.
* You can accumulate several of these and use them whenever the time calls for them. In other words, if you have multiple day passes, you do not need to use them consecutively.
<!-- end -->
### How do these passes work? Does the clock start immediately upon payment, or on the day I initiate the session?
Passes only begin when the controller initiates the session. So if the target's machine fails on them requiring a trip to the shop and a same-day turnaround is not possible, you can simply hold off until the machine is back in good shape and your day pass will still be waiting for you.
### So this means these passes don't expire?
No. Rest assured that your accumulation of day passes will be waiting patiently for you to activate them whenever you're ready.
### What happens if I connect to another machine on the day an incident pass has been used?
That depends. If the machine is within your subscription, I.E. if you're accessing your home machine while on the road, then it's business as usual. Any other connections that aren't the initial target you connected to will work under the usual 30 minute allotment.
### I hold an active one-to-one or one-to-three subscription. Would I still be able to assist a user outside the group for up to 30 minutes, or via a pass?
Yes! Your 30 minute daily allotment is still present for any machine outside of your subscription. Passes are also still available while you hold a subscription.
### I have a one-to-one subscription, and the target computer underwent a hardware upgrade. Will Rim count this as a machine switch?
Only if RIM needs to be reinstalled. So, while a hard drive upgrade or any other situation requiring a Windows reinstallation would be considered a machine switch, upgrading the ram would not.
### Our company bought the pro subscription, but we have two techs - one that does help-desk during the day, and a system maintenance tech that works in the evening. Would we be able to assign the evening sysadmin a controller seat?
Definitely. In situations where multiple technitions will be using RIM, we offer up to two (2) additional controller seats for $50 a month per seat - $500 a year per seat - to accompany the pro plan if needed. This will make it easier for multiple controllers at different workstations or offices to provide remote support.

If you have multiple controller seats, you can purchase additional channels for them so that sessions can run simultaneously. Each additional channel is $50 a month, or $500 a year. Following is a price breakdown for all possible pro plans.
  Number of Controllers | Number of Channels | Price
  ---|---|---
  1 | 1 | $999
  2 | 1 | $1499
  2 | 2 | $1999
  3 | 1 | $1999
  3 | 2 | $2499
  3 | 3 | $2999


## Security
### Are RIM sessions encrypted?
Yes. All sessions, whether they be direct peer-to-peer connections or connections using a relay fallback, are encrypted end to end using Datagram Transport Layer Security (DTLS).
### Do any ports need to be opened on the target or controller?
No and no.
### What connections would need to be allowed on a network in order for RIM to function?
When utilizing the public cloud, an https connection to <https://getrim.app> is required. In optimal cases this is enough for RIM to establish a peer-to-peer connection between the controller and the target. However, it helps to allow UDP connections through ports 19302 and 3478 (the standard STUN and TURN ports). This ensures that if a relay is being utilized, RIM will not have to fall back to a tcp connection on port 443.
The enterprise server for on-premises or VPC deployments listens on the standard https port (443). Port 80 needs to be open as well, though its only purpose is to facilitate https redirect. 
### What background processes does RIM run, and are they light on system resources?
* rim-host-service.exe: target process
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
### What is the minimum version of NVDA required for the client support addon?
The current minimum version required is 2021.3.
### Will the RIM Client Support addon run on a portable copy of NVDA?
Yes, and this includes secure screens since the RIM host process takes care of elevation.
### Can I use the Remote Accessibility Module with the Windows Store version of NVDA?
This is not possible due to the Windows Store version of NVDA not allowing the use of addons. You'll have to either use a portable version of NVDA, or have your IT install the standard version of NVDA on your machine.
### Will my NVDA addons transfer over to this version of NVDA?
Not automatically, and this is generally not advisable anyway. The NVDA included in the accessibility module is designed to be a lightweight, trimmed down, secure solution to provide speech in an environment that otherwise wouldn't have it any other way. That said, if you are using an application for which an NVDA addon is the only way it would be accessible, then you can install that addon individually, though at this point we lack a mechanism to flush the addons directory of all user-generated content upon closing the RIM session. It's worth noting that this version of NVDA contains an addon to communicate with the RIM session, which should not be removed.
## Unattended Sessions
### Are voice conversations supported during unattended sessions?
No.
### If I delete an unattended machine from my controller account, will it automatically revoke permission on the target?
Yes. Once an unattended target is removed, the change will be effective immediately. If the target machine is powered down or otherwise not connected to the internet, the change will be effective as soon as an internet connection is established on their machine.
### The target machine rebooted after installing updates and drivers, and it requires a password to log in. How does the session continue from here?
RIM will attempt to automatically reconnect the session if an installation triggers a reboot. You will also be able to Control+Alt+Delete into the login screen if the target machine requires that.
### I have multiple machines playing the part of the controller. Will the list of machines set up for unattended access populate across all machines?
Yes. The list of machines configured for unattended access is stored within your account, so it will populate automatically.
