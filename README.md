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

🔜 Next Up (Lab 2A-D Preview)
Create OUs
Add IAM users & groups
Set group membership
Create admin accounts
Join a Windows 10 client to the domain


 
 
 
 
 
 🧪 LAB 2A — Active Directory OU, Users & Groups Setup This lab builds a realistic corporate IAM structure inside Windows Server using Organizational Units (OUs), user accounts, and security groups. 
 
 🧠 Objective Build a functional Identity & Access Management (IAM) foundation by creating: - Custom Organizational Units - User accounts - Security groups - Group-based access assignments This mirrors real-world identity lifecycle processes in enterprise environments.
 
 🛠 Tools Used - Oracle VirtualBox - Windows Server 2022 - Active Directory Domain Services (AD DS) - Active Directory Users and Computers (ADUC) 
 
 🚀 LAB 2A — Step-by-Step Instructions 
 **STEP 1 — Open ADUC** Inside DC01: 
 1. Click **Start**
 2. Type: ``` dsa.msc ``` 
 3. Press **Enter** to open **Active Directory Users and Computers**
 
<img width="1036" height="852" alt="Screenshot 2025-11-18 194251" src="https://github.com/user-attachments/assets/caaa34d5-e76b-441c-8f7b-ba39edf4808b" />


 
 **STEP 2 — Expand the Domain** Expand: ``` mylab.local ``` You should see: Builtin, Computers, Domain Controllers, Users, etc. 
 <img width="1078" height="941" alt="Screenshot 2025-11-18 194339" src="https://github.com/user-attachments/assets/ec69ce05-691d-4eae-b490-3f57fe6541a8" />

 **STEP 3 — Create Parent OU** 1. Right-click **mylab.local** 2. Select: ``` New → Organizational Unit ``` 3. Name it: ``` CYBERLABS 
 

 
 **STEP 4 — Create Sub-OUs** Right-click **CYBERLABS → New → Organizational Unit** Create the following OUs: ``` Accounts Computers Security Groups Admins Service Accounts 

<img width="1082" height="881" alt="Screenshot 2025-11-18 225724" src="https://github.com/user-attachments/assets/2fdda47f-3fc5-4d15-8a1d-d82b63677900" />

 **STEP 5 — Create User Accounts** Navigate to: ``` CYBERLABS → Accounts ``` 
 
 ➤ User 1: Lauren Johnson
 1. Right-click **Accounts** → New → User
 2. Enter:  First Name: Lauren Last Name: Johnson User logon name: lauren.johnson 
 3. Set password:  Cyberlab123! 
 4. Settings: - Uncheck: User must change password at next logon - Check: Password never expires
 5. Click **Finish** ---
  <img width="1053" height="868" alt="Screenshot 2025-11-18 230026" src="https://github.com/user-attachments/assets/c8876276-6c17-4151-99bd-c0a775d0aeff" />

 7. ➤ User 2: Os Williams
 1. Repeat the same process: 
 2. First Name: Os Last Name: Williams User logon name: os.williams
 3. Password: Cyberlab123! 
 4. Settings: - Uncheck: User must change password at next logon - Check: Password never expires

<img width="1064" height="892" alt="Screenshot 2025-11-18 230305" src="https://github.com/user-attachments/assets/e791caf0-f515-42a6-b527-f1f728d8bd9e" />

     **STEP 6 — Create Security Groups**
 1. Navigate to: ``` CYBERLABS → Security Groups ```
 2. Right-click → New → Group  Create the following groups: ``` Group Name: HR-Team Scope: Global Type: Security ``` ``` Group Name: IT-Admins Scope: Global Type: Security ``` ``` Group Name: All-Staff Scope: Global Type: Security
 <img width="1065" height="892" alt="Screenshot 2025-11-18 230430" src="https://github.com/user-attachments/assets/333af807-e44f-4939-8f77-12aa1efa853a" />


 **STEP 7 — Add Users to Groups** 
 ➤ Add Lauren Johnson Add her to: ``` HR-Team All-Staff ``` Steps: 
 1. Double-click **Lauren Johnson**
 2.  Select **Member Of**
 3.   Click **Add**
 4.    Enter: ``` HR-Team All-Staff ```
 5. Click **Check Names → OK**

    <img width="1078" height="892" alt="Screenshot 2025-11-18 230631" src="https://github.com/user-attachments/assets/0732f185-55af-4a27-bdcb-b39e9dca2e99" />

  
 ➤ Add Os Williams Add him to: ``` IT-Admins All-Staff ``` Steps: 
 1. Double-click **Os Williams**
 2. Member Of → Add
 3. Enter: ``` IT-Admins All-Staff ```
 4. Check Names → OK
📸 Screenshot: Os’s Member Of tab
<img width="1081" height="907" alt="Screenshot 2025-11-18 230718" src="https://github.com/user-attachments/assets/21169773-8bbc-474f-ab64-b82551657743" />

 ✅ Validation Checklist Your Lab 2A is **Sucessfully completed** if: ✔ CYBERLABS parent OU exists ✔ Accounts, Computers, Security Groups, Admins, Service Accounts exist ✔ Users Lauren Johnson + Os Williams exist in Accounts ✔ Groups HR-Team, IT-Admins, All-Staff created ✔ Correct group membership assigned 
 📸 Optional Screenshot: Full OU tree expanded 
 
 🧠 Concept Notes (Short & Easy) Active Directory is the central identity directory for Windows environments.Organizational Units (OUs) help organize identities and apply policies.Custom OUs are best practice—never use default “Users” or “Computers. User accounts represent real employee identities. Security Groups enforce RBAC (Role-Based Access Control). Adding users to groups determines their access across systems. This lab simulates how IT and HR manage access in real organizations.  !!!END OF LAB 2A You now have a functional IAM structure ready for workstation domain joins, GPOs, and access control labs.




 # 🧪 Lab 2B — Small Business OU Structure **Domain:** mylab.local **Server:** DC01 — Windows Server 2022 
 
 🎯 Objective Design a simplified Active Directory structure appropriate for a small business environment. Ensures: - Easy management for small IT teams - Clean user identity separation - Basic workstation/server organization - Support for RBAC (Role-Based Access Control) 
 
 
 🧱 Final OU Structure 
 mylab.local: 
    -OU_Employees
        -OU_Admins
        -OU_StandardUsers 
    -OU_Computers
        -OU_Workstations
        -OU_Servers 
    -OU_Groups 
    
    📌 Naming Standard: All custom OUs begin with **OU_** ➡ Helps identify objects managed by IAM team  
    🛠 Steps Performed:
    1. Open Active Directory Users and Computers (ADUC) - Start Menu → Search: **Active Directory Users and Computers** - Press Enter 

<img width="1087" height="439" alt="Screenshot 2025-11-19 195641" src="https://github.com/user-attachments/assets/62d6d512-bd53-4c07-a53b-d55da54226dd" />

    2️. Enable Advanced Features Required to manage additional directory object properties. - Top menu → **View → Advanced Features** 

    <img width="1049" height="424" alt="Screenshot 2025-11-19 195836" src="https://github.com/user-attachments/assets/e2b28d18-332e-4da7-ab27-e307e13906f6" />
    

    3️. Create OU_Employees 
    -Right-click **mylab.local** → New → Organizational Unit 
    -Name: **OU_Employees** 
    -nsure “Protect object from accidental deletion” is checked 
    -Click OK 📸 Screenshot — OU_Employees created 
    
    4️. Create Sub-OUs in OU_Employees Inside **OU_Employees**: 
    -OU_Admins 
    -OU_StandardUsers (Each created via: Right-click OU → New → Organizational Unit) 
    
    5️.Create OU_Computers 
    -Right-click **mylab.local** → New → Organizational Unit  
    -Name: **OU_Computers**  
    6️. Create Sub-OUs in OU_Computers Inside **OU_Computers**:  
    -OU_Workstations 
    -OU_Servers  
    
    7️. Create OU_Groups 1. Right-click **mylab.local** → New → Organizational Unit 2. Name: **OU_Groups** 📸 Screenshot — OU_Groups created 
    
    
    <img width="1036" height="892" alt="Screenshot 2025-11-19 193903" src="https://github.com/user-attachments/assets/ff13ac5e-955f-42fd-be51-725bcd3fd2c1" />

     ✔ Validation Checklist Your Lab2B **Sucessfully completed** 
   OU Structure Complete
   Advanced Features Enabled 
   Naming Standards Applied 
   Structure Ready for Group Policies 

    🧠 Concept Notes Identity & Access Management Takeaways:  Small businesses need **simplified OU design** to reduce support complexity  Separation between **admins and standard users** supports **least privilege**  Organizing servers separately enables **stricter security policies**  Keeping security groups in a **dedicated OU** supports clean RBAC **Protection against deletion** prevents accidental outages in production AD. This OU model matches real-world MSP and small enterprise environments.
   
  
