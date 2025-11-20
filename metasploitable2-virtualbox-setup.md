# Metasploitable 2 Home Lab Setup (Using VirtualBox)

This guide provides a step-by-step process for deploying the **Metasploitable 2** vulnerable virtual machine in a home lab environment using **Oracle VirtualBox**.  
This VM will be used as a target for:

- Testing Suricata IDS/IPS rules
    
- Validating detections inside your SIEM
    
- Practicing penetration testing and vulnerability assessment
    

---

## 1. Download Metasploitable 2

**Metasploitable** is an intentionally vulnerable Linux VM created by Rapid7 for safe and legal security testing.

Official documentation:  
[https://docs.rapid7.com/metasploit/metasploitable-2/](https://docs.rapid7.com/metasploit/metasploitable-2/)

Download the VM ZIP package:

`https://downloads.metasploit.com/data/metasploitable/metasploitable-linux-2.0.0.zip`

After downloading, extract the archive using WinRAR, 7-Zip, or a similar tool.

---

## 2. Extract the VM Files

The extracted folder contains:

- `metasploitable.vmdk` – virtual machine hard disk
    
- Additional VirtualBox configuration files
    

These files will be used when creating the VM in VirtualBox.

---

## 3. Create a Virtual Machine in VirtualBox

1. Open **Oracle VirtualBox**.
    
2. Navigate to:
    

`Tools → New`

3. Enter the following details:
    

- **Name:** Metasploitable2
    
- **Machine Folder:** Choose your preferred storage path
    
- **Type:** Linux
    
- **Version:** Other Linux (32-bit)
    

---

## 4. Attach the Existing Virtual Disk

1. Expand the **Hard Disk** section.
    
2. Select **Use an existing virtual hard disk file**.
    
3. Click the folder icon.
    
4. In the selector window, click **Add**.
    
5. Browse to the extracted folder and select:
    

`metasploitable.vmdk`

6. Click **Choose**, then **Finish**.
    

VirtualBox will now create the VM using this disk.

---

## 5. Configure Network Settings

To ensure your lab environment is consistent, change the network mode to **Bridged Adapter**.

1. Right-click the VM → **Settings**
    
2. Go to **Network**
    
3. Set **Attached to:** Bridged Adapter
    
4. Click **OK**
    

This allows the VM to receive an IP address from your LAN, making it accessible to other lab systems.

---

## 6. Start the Metasploitable VM

1. Select the VM.
    
2. Click **Start**.
    

Once the VM boots, you will see a login prompt.

Default credentials:

`username: msfadmin password: msfadmin`

Log in with these credentials.

---

## 7. Retrieve the Server’s IP Address

Inside the VM, run:

`ifconfig`

Identify the IP address assigned to the VM.

Example:

`192.168.1.150`

This IP address will be used to access the vulnerable applications.

---

## 8. Access the Metasploitable Web Applications

On your host machine:

1. Open a web browser.
    
2. Navigate to:
    

`http://<metasploitable-ip>`

Example:

`http://192.168.1.150`

If the page does not load, wait **2–3 minutes** for all vulnerable services to finish starting.

You will then see the Metasploitable 2 landing page, which includes access to applications such as:

- DVWA
    
- Mutillidae
    
- WebDAV directories
    
- phpMyAdmin
    
- Many more vulnerable services
    

---

## ✅ Your Metasploitable Lab Target Is Ready

You now have a fully functional **Metasploitable 2** instance running in your lab environment. This VM can now be used for:

- Suricata IDS/IPS rule testing
    
- SIEM alert correlation and validation
    
- Vulnerability scanning
    
- Penetration testing practice
    
- Red, Blue, and Purple Team simulations
