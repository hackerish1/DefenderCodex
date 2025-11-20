Metasploitable 2 Home Lab Setup (Using VirtualBox)

This guide provides a step-by-step process for deploying the Metasploitable 2 vulnerable virtual machine in a home lab environment using Oracle VirtualBox.
This VM will serve as a target for testing Suricata rules, validating detections in your SIEM, and practicing penetration testing techniques.

1. Download Metasploitable 2

Metasploitable is an intentionally vulnerable Linux VM created by Rapid7 for safe and legal security testing.

Official documentation:
https://docs.rapid7.com/metasploit/metasploitable-2/

Download the VM zip package from the official Rapid7 repository:

Metasploitable 2 (VMDK ZIP):
https://downloads.metasploit.com/data/metasploitable/metasploitable-linux-2.0.0.zip

After downloading, extract the contents using any tool such as WinRAR or 7-Zip.

2. Extract the VM Files

Once extracted, the folder will contain the following:

metasploitable.vmdk – virtual machine hard disk file

Additional VirtualBox VM configuration files

These files will be used when importing the VM into VirtualBox.

3. Create a Virtual Machine in VirtualBox

Open Oracle VirtualBox.

Navigate to:

Tools → New

Fill out the VM details:

Name: Metasploitable2

Machine Folder: Choose your desired storage path

Type: Linux

Version: Other Linux (32-bit)

Attach the Existing Virtual Disk

Expand the Hard Disk section.

Select Use an existing virtual hard disk file.

Click the folder icon to open the disk selector.

Click Add → browse to the extracted folder.

Select the file:
metasploitable.vmdk

Click Choose, then click Finish.

VirtualBox will now create the Metasploitable VM using the existing disk.

4. Configure the VM Network Settings

To ensure your lab environment is consistent, update the network mode to Bridged Adapter.

Right-click the virtual machine → Settings

Go to Network

Set Attached to: Bridged Adapter

Click OK

Bridged mode ensures the Metasploitable VM receives an IP from your LAN, making it accessible from other lab systems.

5. Start the Metasploitable VM

Select the Metasploitable VM and click Start.

The VM may take a few moments to boot. Once loaded, you will see the login prompt.

Default credentials:

username: msfadmin
password: msfadmin


Log in using these credentials.

6. Retrieve the Server’s IP Address

After logging in, run:

ifconfig


Locate the IP address assigned to the VM.
Example:

192.168.1.150


You will use this IP to access the vulnerable web applications.

7. Access the Metasploitable Web Applications

On your host machine, open a web browser.

Navigate to:

http://<metasploitable-server-ip>


Example:

http://192.168.1.150


If the page does not load immediately, wait 2–3 minutes for all services to fully start.

Once loaded, you will see the Metasploitable landing page, which contains links to numerous intentionally vulnerable applications such as:

DVWA

Mutillidae

WebDAV directories

phpMyAdmin

And more

Your Metasploitable Lab Target is Ready

You now have a fully functional Metasploitable 2 instance running in your lab environment. This VM can now be used for:

Suricata IDS/IPS rule testing

SIEM correlation and alert validation

Vulnerability scanning

Penetration testing practice

Red/Blue/Purple team simulations

If you want, I can also create a companion Suricata rule testing walkthrough, SIEM validation workflow, or network diagram in the same documentation style.
