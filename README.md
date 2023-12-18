<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>File Shares)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>

![image](https://github.com/MartindIT/network-fileshare/assets/151476834/dae20480-b169-4fcb-bcbd-c860edf481fa)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/f8222b87-381c-483b-b4a8-e7a143288e05)

**1.) First we need to login as Jane Doe on Domain Controller VM then go to "Active Directory Users and Computers" then go to Employees and pick a random account and log in as that person through Client-1 VM.**

![image](https://github.com/MartindIT/network-fileshare/assets/151476834/6324f71c-c9e1-4fe6-b2bb-1290d0a5a2c7)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/b33d5b69-74ad-432f-a759-d25e2d771ebe)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/3f70727f-2b97-4875-adac-a233b49f6187)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/ca1f6abb-614f-49e5-93ef-ddcd97e146a0)


**2.) Then go back into Domain Controller VM and make four folders called "Read Access, Write Access, No Access, Accounting" and give them proper permissions. *you can skip accounting for now*** 

![image](https://github.com/MartindIT/network-fileshare/assets/151476834/297d3f3c-d502-4c5c-9f96-11c6168103d4)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/5afff6d7-83be-4359-a2c6-296c37517a9a)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/cdbe3cec-e05e-446e-b845-5e39eeae813b)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/526f19c1-a994-436e-872f-fb0f44b93c45)

**3) Now when we go into Client VM and type our Domain Controller VM these folders pop up and as you can see we dont have all permissions because we are "sox.tot" and this just a normal account with no admin privileges.**

![image](https://github.com/MartindIT/network-fileshare/assets/151476834/65e8ac9f-8b73-4ed0-a9dc-55d30761ed3f)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/733af8ba-f85f-40b8-8480-a2c83d607425)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/75a05318-47b8-41af-a7ad-a763d2d13e37)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/55132190-0e0c-4b5d-a4be-a84a04f5233e)


**4.) Now go back to Domain Controller VM and go to active directory and make another org unit called "Security Groups" and right click and make new group call this group "Accountants" and then go to your files and go to the accounting file we created earlier and assign permissions to the Acountants with read and write.**

![image](https://github.com/MartindIT/network-fileshare/assets/151476834/fbccceab-c0fb-486b-a123-ba03400ccf66)
![image](https://github.com/MartindIT/network-fileshare/assets/151476834/b5e7bff4-81da-44c1-a330-c11a7ab095a1)

**5.)Finally just add your fake account as a member of Accountants and then go back to Client-1 VM and browse into the Accountants Folder.



