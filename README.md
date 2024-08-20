![image](https://github.com/user-attachments/assets/d349eede-2922-4dfe-a308-a22537c0e02c)

<h1>Understanding File Permissions</h1>
This activity focuses on file permissions and shares within an Active Directory domain. Proper management of file permissions and shares is crucial in an enterprise environment to ensure that users have appropriate access to necessary files. 

<h2>Technologies and Platforms</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Active Directory Domain Services

<h2>Operating Systems</h2>

- Windows 10 Pro (22H2)
- Windows Server 2022

<h2>File Permissions Configuration</h2>

![image](https://github.com/user-attachments/assets/192cdc20-b55d-43a2-b06c-a4ab14b3a649)
![image](https://github.com/user-attachments/assets/d22589e7-3e33-4d28-bc05-cd9681ce974a)

<p>
To set permissions for files and folders, I first created the folders to be shared. While logged into the domain controller VM as an administrator, I created the folders on the C:\ drive. I then accessed the folders' properties, adjusted their permissions, and used the Sharing tab to specify network users and assign appropriate permissions.

Domain Users have Read access to the read-access folder and Read/Write access to the write-access folder. Domain Admins have Read/Write access to the no-access folder. 
</p>

![image](https://github.com/user-attachments/assets/c68e772f-e255-4848-b14e-53271cf77752)

<p>
On the client VM, navigate to the :\dc1 path in File Explorer to access the shared folders created on the domain controller. Here, you can view the permissions assigned to these folders, such as read-only access or no access at all. These permissions are relative to the Security Group to which the domain user belongs. 
</p>

![image](https://github.com/user-attachments/assets/cde8862a-f126-4636-a380-285137dae311)
![image](https://github.com/user-attachments/assets/2400a78a-2556-4cc6-b7f3-b27db39b7d00)

<p>
Next, I will configure the accounting folder by creating a new Security Group and assigning the appropriate permissions. On the domain controller, in Active Directory Users and Computers, I will create the "ACCOUNTANTS" group and grant it Read/Write permissions for the designated folder. 
</p>

![image](https://github.com/user-attachments/assets/f144529d-99d5-4322-8327-d2fd70c1e926)
![image](https://github.com/user-attachments/assets/61276c68-27a0-4310-a424-5cf75110092c)

<p>
Since the user is not a member of the ACCOUNTANTS security group, they currently cannot access the folder. To resolve this, in Active Directory on the domain controller, navigate to the ACCOUNTANTS group properties and add the user (tob.vila) to the group. Once logged back into the client, tob.vila will gain access to the accounting folder. 
</p>

<h2>Key Takeaways</h2>
This activity reinforced my understanding of file permissions management through Windows Active Directory in a professional setting. In IT, I will often need to configure permissions and add users to ensure they have the necessary access to perform their tasks. 
