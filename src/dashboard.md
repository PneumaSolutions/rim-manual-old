# The RIM Management Dashboard
RIM features a  web-based dashboard to facilitate various machine and account management tasks. You can manage your existing unattended computers, create preconfigured installers for target computers, and much more.  
It should be noted that the feature set of the dashboard is largely dependent on which subscription tier your account is under. For example, enterprise users can assign machines to target groups, as well as create silent installers. On the other hand, anyone (including personal users) can create custom installers for their unattended machines.
## Locating the Dashboard
If you're a controller, the easiest way to get to the dashboard is through the main RIM interface. Clicking the RIM Dashboard button will automatically open the dashboard in your default browser, with the login already taken care of.  
If you are a network administrator who does not have RIM installed, you can simply log into your account on the RIM website and your dashboard will appear.
## Managing Targets
When you click the "Configure Targets" link, you will arrive at a page that allows you to manage all the machines you have configured for unattended access. You can click on any one of these machines in order to manage it. Once inside, you will be able to:
* Rename the target
* Move the target to a different group (more on target groups later)
* Delete the target
<!-- end -->
## Target Groups (for Pro Accounts and Above)
Say for instance you're workgroup is spread out among several different locations. Or maybe you want to designate groups of machines to your routine maintenance techs. Target groups allow you to do just that. In order to do this, simply click the "Create Target Group" button, name your group, and submit.  
You may have as many target groups as is needed for your use case. 
## Setting up a Preconfigured RIM Installer
One of the easiest ways to set up a machine for unattended or prompted connections is by creating a custom installer. This is incredibly useful if you are configuring mass deployments, or even as a simpler way to get RIM up and running on an end user's computer you plan on providing support for on the regular.
IN order to do this:
1. In the target management screen, click the "Build Target Installer" button.
1. You will first be asked if you want this machine to be configured as fully unattended, or for prompted access in which the user has to accept a prompt to initiate the connection.
1. You will then be asked for a target group assignment. Note that the target group selection will automatically go to your chosen target group if you initiate the installer configuration from your group's page.
1. You will be asked how long you want this installer to be valid for. It can be valid for anywhere between 7 to 30 days. Note that this timeframe only affects the functionality of the installation package. In other words, the machine's RIM configuration will not be disabled when the installation expires.
1. You are then given the option to assign a bass name to all machines designated to this target group.
1. If you are an enterprise admin, you will see a checkbox that allows you to build the installer as an MSI package. This option is useful for mass deployment of a custom installer to a machine cluster that will be designated to the given target group.
1. Click on "Build Installer." You will be presented with the download link that you can either copy to the clipboard and send to your end user, or you may download the installer directly for use in mass deployments.
<!-- end -->
Now that you have your installer, it can be run in one of two ways. In either case, the machine will be added to your list of machines in both your account as well as the RIM client after the installer is complete.
### Normal Execution
The user will get a prompt when running the installer, containing the following information:
* The technician's name
* the nature of the connection, I.E whether a prompt is required or not
<!-- end -->
The user can choose to either answer yes or no to the installation. Answering no will cancel the installation. After the installer finishes, the user will get a prompt informing them that their machine is now set up for remote access.
### Silent Install (Enterprise Installers Only)
A silent install can be initiated by running the executable installer with the */S* command line parameter. This is useful when installing RIM as part of a mass deployment routine.
## Session History
You can view your entire history of past sessions through the RIM dashboard. The session history currently contains the date and time of each session, the name of the computer you connected to, and the duration of the session.