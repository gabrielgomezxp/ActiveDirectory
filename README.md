<h3>This lab is a small guide on how to implement Active Directory</h3>

![image](https://github.com/user-attachments/assets/c9a931a5-c093-49f8-861e-0e191907d859)
 - Our first step is to create two virtual machines, a client based VM running Windows 10, and a Server VM running on Windows Server.

![image](https://github.com/user-attachments/assets/d6e7ed3d-6820-47f1-a6ad-0f5405fc8c84)
 - Next we will connect to our dc server using **Remote Desktop Connection** using the created credentials and open up our server manager where we will **Add roles and features**. Continue to hit next until you reach **Server Roles** and make sure to check the box that says **Active Directory Domain Services**.

![image](https://github.com/user-attachments/assets/174f6ce1-acbd-4b7e-989f-ee2e0397e72b)
  - After we have implemented our Active Directory Domain Services, restart the dc VM, open Server Manager, and click on the little yellow flag on the top right corner and select **Promote this server to a domain controller**. Once our Deployment Configuration settings open up, be sure to select **Add a new forest** with a root domain name of **mydomain.com**. Once youre asked for credentials just go ahead and type **Password1** since this will never be used again. In our DNS Options, uncheck **Create DNS delegation** and continue to hit next until fully installed.

![image](https://github.com/user-attachments/assets/e45d8b0f-f003-45b2-bf8b-8f409f28ebfa)
 - Once our VM has restarted, we will now need to specify a user when logging into our domain controller. In this case, mydomain.com\labuser.

![image](https://github.com/user-attachments/assets/c5fc09cb-2bc3-4c34-88a0-7fe4f8101315)
 - Step 5, we will navigate to **Active Directory Users and Computers**, right click inside of the mydomain.com folder, hit New and create two Organizational Units named **_EMPLOYEES** & **_ADMINS**.

![image](https://github.com/user-attachments/assets/ca435c99-c1b2-4496-b3de-40ec53af82a9)
 - Next we will right click inside the **_ADMINS** folder and create a user named **Jane Doe** with a log on of **jane_admin**, create a password and hit next until completed.

![image](https://github.com/user-attachments/assets/631cff7b-5536-452f-9748-a0cf8eb98df0)
 - We will now give **Jane Doe** admin permissions by right clicking **Jane Doe** in our **_ADMINS** folder and following <h4>Properties > Member Of > Add... > Enter the object names to select > Type **Domain Admins** > Check Names > OK. </h4>
 Now our **Jane Doe** account has admin permissions.
