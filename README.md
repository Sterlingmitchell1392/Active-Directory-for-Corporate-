<h1>Active Directory Corporate Environment in Oracle VirtualBox</h1>



<h2>Description</h2>
Project consists of a building  a Active Directory Environment in Oracle VirtualBox and using Powershell script to generate 1000 users instead of doing so manually and adding the VM client (coporate) to the created domain internet NAT


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Command Line </b>

<h2>Environments Used </h2>

- <b>Windows 11</b> (21H2)
-  <b>Oracle VirtualBox</b> (21H2)

<h2>Program Diagram:</h2>

![Image](https://github.com/user-attachments/assets/b8778b7b-774c-4ea1-b132-d0f4b35ac99c)

-For network diagram, we have two NICs one dedicated to the Internet attached to NAT and the other dedicated to internal VM

![Image](https://github.com/user-attachments/assets/437f81de-61f7-46b0-a48a-bbbd28a0df82)

-Next step is to install Windows Server 2019 on the VM.

![Image](https://github.com/user-attachments/assets/137adedf-88b1-4713-aed8-13c130e8fe4e)

Next Update and change the IPv4 Internal to match the diagram NIC internal ip

![Image](https://github.com/user-attachments/assets/7b39fe33-35c9-4a30-ab38-190e9d731d93)

![Image](https://github.com/user-attachments/assets/97d740d8-4dbc-44c6-9107-b642f2dfbd47)

-Install active directory domain service and create a domain.

![Image](https://github.com/user-attachments/assets/1e76c2bc-a4c6-443c-afb5-03d5d5c63940)

-Create a domain name

![Image](https://github.com/user-attachments/assets/6cf7de86-9049-44b7-a957-66971d4f3593)

-After installed you will see MyDomain/Administrator whenever you log in.

![Image](https://github.com/user-attachments/assets/447bbe48-7769-4373-8e77-6e9fe4735a16)

-Next create a Organization Unit to put your admin account in

![Image](https://github.com/user-attachments/assets/98458bdf-d4dc-4f0a-81e0-c2d8103f17dc)

-Create a profile for user and add user to domain

![Image](https://github.com/user-attachments/assets/c1355feb-300c-47a0-8885-d479b7a31f22)

![Image](https://github.com/user-attachments/assets/724c6af4-2135-4254-a1c7-241b0c430285)

-Sign in with new user account

![Image](https://github.com/user-attachments/assets/7423e746-d210-4767-a440-1faebb096920)

-Next, install the Remote Access Server and  Network Address Translation on domain controller. The purpose is to allow client access a private IP through the Internet domain controller

![Image](https://github.com/user-attachments/assets/72bc0d80-b887-41df-bc86-d1406d30cb89)
![Image](https://github.com/user-attachments/assets/723d5041-c9ad-41b4-b8d6-65b47c3ebf62)


-Review Network Setup after

![Image](https://github.com/user-attachments/assets/a24dad3a-23d5-4040-a6ed-790f1dc78f39)

-Setup DHCP on domain controller to allow clients to gain Internet connection

![Image](https://github.com/user-attachments/assets/9b9d5c5d-e794-4ce2-a732-3b95cb700c33)

-Create a scope that will give IP addresses in the range created.

![Image](https://github.com/user-attachments/assets/f7ccadc7-5878-4b5e-826e-bc2e8c2fcc19)

![Image](https://github.com/user-attachments/assets/8e7cdada-d463-4c82-9dfd-6227c8876850)

-Next, enter and add the Domain controller IP if 172.16.0.1 and click ADD!

![Image](https://github.com/user-attachments/assets/3ec81ae3-7dab-44b1-bd75-8c69b415a774)


-Next, use Powershell scripts to create 1000 users in active directory to avoid manually creating them!

![Image](https://github.com/user-attachments/assets/164e389b-439b-453a-9001-b5c3c9ad58f2)
![Image](https://github.com/user-attachments/assets/bd485b9d-e409-4d38-8640-238d8b7f5f60)

-Run script

![Image](https://github.com/user-attachments/assets/1679ecda-e69c-4881-905c-25f36e12d1e7)

-Review active directory with new users after script completed

![Image](https://github.com/user-attachments/assets/13db7b83-ad01-4c89-b5e6-03f7bd826049)

-Last thing, create Windows 11 virtual machine in virtual box

![Image](https://github.com/user-attachments/assets/76ca3e40-bb40-4ffd-8b8c-24f710b90806)

-Add client domain to MyDomain.com. this can be confirmed under address leases in DHCP.

![Image](https://github.com/user-attachments/assets/0b50a09f-d78a-41a9-adb4-c7e56fbe8a8d)

![Image](https://github.com/user-attachments/assets/487675fe-4211-4015-a499-7d0f1dab47e5)

-Confirm info in  Command line  

![Image](https://github.com/user-attachments/assets/54a58b50-fc0b-4bef-a5c0-493cde97fbb0)
