# Wazuh Home Lab Setup (Using the Wazuh OVA)

This guide provides a step-by-step process for deploying a Wazuh server in a home lab environment using the official Wazuh OVA file and Oracle VirtualBox.

---

## 1. Download the Wazuh OVA

Wazuh provides detailed documentation for virtual machine deployments. You can reference it here:

- Wazuh VM Deployment Docs:  
    [https://documentation.wazuh.com/current/deployment-options/virtual-machine/virtual-machine.html](https://documentation.wazuh.com/current/deployment-options/virtual-machine/virtual-machine.html)
    

Download the OVA file:

- **Wazuh OVA (4.14.1)**:  
    [https://packages.wazuh.com/4.x/vm/wazuh-4.14.1.ova](https://packages.wazuh.com/4.x/vm/wazuh-4.14.1.ova)
    

---

## 2. Import the OVA File into VirtualBox

1. Open **VirtualBox**.
    
2. Navigate to **Tools** → **Import**.
    
3. In the Import screen, open the **File Explorer**.
    
4. Browse to the directory where you downloaded the Wazuh OVA file.
    
5. Select the OVA file and proceed by clicking **Next** or **Finish**.
    

VirtualBox will now begin importing the appliance. This may take a few minutes.

---

## 3. Review Default VM Settings

After the OVA import completes, review the preconfigured settings:

- **Base Memory:** 8192 MB
    
- **Processors:** 4
    
- **Network Adapter:** Bridged Adapter
    

You may adjust these values based on your system resources, but the defaults work well for testing.

---

## 4. Start the Wazuh Virtual Machine

1. Select the imported **Wazuh Server** VM.
    
2. Click **Start**.
    

Once the VM boots successfully, you should see a CLI login screen displaying the default credentials:

`User: wazuh-user Password: wazuh`

Log in to the server using these credentials.

---

## 5. Retrieve the Server’s IP Address

After logging in, run:

`ifconfig`

Locate the IP address assigned to the server.  
For example:

`192.168.1.76`

---

## 6. Access the Wazuh Web Interface

1. On your host machine, open a web browser.
    
2. Navigate to:
    

`https://<wazuh-server-ip>`

Example:

`https://192.168.1.76`

You will encounter a certificate warning. Select **Advanced** → **Proceed** to continue.

---

## 7. Log In to the Wazuh Dashboard

Use the default dashboard credentials:

`Username: admin Password: admin`

After successful authentication, you will be redirected to the Wazuh home dashboard.

---

You now have a fully functional Wazuh server running in your home lab. This environment can be used for security monitoring, log analysis, threat detection experiments, and more.
