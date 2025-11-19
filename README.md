# 🧠 Cybersecurity Labs by Andranette Freeman

Welcome to my cybersecurity lab documentation!

This repository showcases hands-on exercises I’ve completed while studying **Identity & Access Management, Azure Security, and CompTIA Security+ topics**. 

 📚 Lab Categories - **IAM Labs** → Azure Entra ID, RBAC, Conditional Access - **Network Security Labs** → Firewalls, VPNs, Packet Capture - **System Security Labs** → Virtual Machines, Hardening, Patch Management🧩 Purpose To document and demonstrate real-world skills for future cybersecurity roles.

 🧪 LAB 1 - Install & Configure Windows Server 2022 Domain Controller (DC01) **Platform:** Oracle VirtualBox **Purpose:** Build the foundation of an IAM home lab by installing Windows Server 2022 and promoting it to a Domain Controller for the domain **mylab.local**.  

 🔰 Overview This lab sets up the core Active Directory environment needed for future IAM, SC-300, and cybersecurity labs. You will create a VM, install Windows Server 2022, configure networking, install AD DS, and promote the server to a domain controller.  

 📌 1. Create the Windows Server VM Steps Performed 
1. Open **Oracle VirtualBox**.
2.  Click **New**.
3.   Enter: - **Name:** `DC01` - **ISO Image:** Windows Server 2022 ISO - **Type:** Microsoft Windows - **Version:** Windows Server 2022 (64-bit)
4.    Click **Next**.
5. Configure hardware: - **RAM:** 4096 MB - **Processors:** 2 - **Hard Disk:** 50 GB (VDI)
6.  Click **Finish**. 
   
<img width="846" height="814" alt="Screenshot 2025-11-17 170601" src="https://github.com/user-attachments/assets/2fcc7271-e3d9-4933-bebf-60b5d0975ef3" />

10.  📌 2. Install Windows Server 2022 Steps Performed
11.  1. Start the DC01 VM.
     2. Choose language/region → **Next**.
     3.  Click **Install Now**.
     4.   Select: **Windows Server 2022 Standard (Desktop Experience)**
     5.    Accept license → choose **Custom Install**.
     6. Select the 50 GB virtual disk → **Next**.
     7.  Allow installation to complete and reboot.
            <img width="864" height="85" alt="Screenshot 2025-11-17 171820" src="https://github.com/user-attachments/assets/5cca1a6c-1ec9-4982-89a6-93f400043639" />

      📌 3. Set Administrator Password & Log In  Steps Performed
      1. Create a password for the built-in **Administrator** account.
      2.  Press: **Input → Keyboard → Insert Ctrl+Alt+Del**
      3.   Log in using: - **Username:** Administrator - **Password:** (your password) 
     
      .<img width="1116" height="876" alt="Screenshot 2025-11-17 151833" src="https://github.com/user-attachments/assets/4d506f59-8c0e-468c-abcf-e0e294279aee" />

      📌 4. Configure a Static IP Address Active Directory requires a stable, non-changing IP address. Steps Performed
      1. Inside DC01, open: **Control Panel → Network & Internet → Network Connections**
      2.  Right-click **Ethernet** → **Properties**.
      3.   Double-click **Internet Protocol Version 4 (TCP/IPv4)**.
      4.    Enter the following static IP settings: | Setting | Value | |--------|--------| | IP Address | **192.168.4.10** | | Subnet Mask | **255.255.255.0** | | Default Gateway | **192.168.4.1** | | Preferred DNS | **127.0.0.1** | | Alternate DNS | *(blank)* |
      5. Click **OK**, then **Close**. 
      6. 
      .<img width="1044" height="837" alt="Screenshot 2025-11-17 154826" src="https://github.com/user-attachments/assets/d0ff7271-557c-42a0-9e22-cbfb8a2c4e68" />

 
      8.
     📌 5. Verify IP Assignment  Command Used ```cmd ipconfig ``` Expected Output - IPv4 Address: **192.168.4.10** - Default Gateway: **192.168.4.1** 

 <img width="1030" height="661" alt="Screenshot 2025-11-17 162315" src="https://github.com/user-attachments/assets/af2cb183-cbb1-4028-879b-00cdf06071d6" />

 
 📌 6. Test Network Connectivity  Command Used ```cmd ping 192.168.4.1 ```  Expected Result: Successful replies (0% loss)
 
<img width="1035" height="656" alt="Screenshot 2025-11-17 162522" src="https://github.com/user-attachments/assets/64f88d7c-785a-4218-a084-6cc401013889" />

 
 📌 7. Install Active Directory Domain Services (AD DS) #Steps Performed 
 1. Open **Server Manager**.
 2.  Click **Manage → Add Roles and Features**.
 3.   Select: - **Role-based or feature-based installation** - Server: `DC01`
 4.    Check **Active Directory Domain Services**. 5. Click: - **Add Features** - **Next → Next → Install**
   
<img width="1235" height="897" alt="Screenshot 2025-11-17 164422" src="https://github.com/user-attachments/assets/54670081-25da-4a6c-9c18-1b314386f18c" />

 📌 8. Promote Server to Domain Controller Steps Performed
  1. In Server Manager, click the **yellow flag** notification.
  2.  Select **Promote this server to a domain controller**.
  3.   Choose: - **Add a new forest** - **Root domain name:** `mylab.local`
  4.    Enter DSRM password.
  5. Click **Next** through remaining pages.
  6.  Ignore DNS warning (normal).
  7.   Click **Install**.
  8.    Server automatically reboots. 📝 Note I did not capture the *Prerequisite Check Passed* screen, but AD DS promotion was confirmed via Server Manager notifications.

<img width="1111" height="881" alt="Screenshot 2025-11-17 165116" src="https://github.com/user-attachments/assets/fa6c4028-9b89-4045-aa44-009049d40d27" />

 11. 
 12.  # 📌 9. Verify Domain Controller Status Steps Performed 
 1. Log in using: ``` Username: mylab\Administrator ```
 2.  Open **Server Manager → AD DS**.
 3.   Confirm: - Domain: **mylab.local** - Server: **DC01** - DNS installed - No critical errors ---

 <img width="846" height="814" alt="Screenshot 2025-11-17 170601" src="https://github.com/user-attachments/assets/760dec2d-6bc5-4927-a2a4-52f2a5ad7555" />

  
 14.    🎉 LAB 1 — COMPLETED SUCCESSFULLY Accomplishments - 🖥 Windows Server VM created - 🌐 Static IP configured - 📡 Network connectivity verified - 🏰 AD DS installed - 👑 Server promoted to Domain Controller for **mylab.local** - 🧩 Environment ready for IAM & SC-300 labs --- # 🔜 Next Lab (Lab 2 Preview) - Create Organizational Units (OUs) - Add IAM users & groups - Set group membership - Create admin accounts - Prepare a Windows 10 client to join the domain

🧠 Lab 1 — Concept Summary (1 Paragraph) In this lab I built the foundation of an IAM environment by creating a Windows Server 2022 virtual machine and promoting it to a Domain Controller. I used VirtualBox to simulate a real company network, installed Windows Server because it supports Active Directory Domain Services (AD DS), and configured a static IP so the DC is always reachable. I set DNS to the domain controller itself because Active Directory depends on DNS to find identity services. Bridged networking allowed the server to communicate like a real device on my home network. This created the core identity system (mylab.local) where all users, groups, permissions, and authentication will be managed in future labs.

🔜 Next Up (Lab 2 Preview)
Create OUs
Add IAM users & groups
Set group membership
Create admin accounts
Join a Windows 10 client to the domain
