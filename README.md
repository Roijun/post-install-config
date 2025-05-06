<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create an Azure Virtual Machine Windows 10

<p>Within the Azure envirnoment, create a Virtual Machine(VM) with at least 8GB of RAM to house as the location for the osTicket installation process.  </p>
  
  ![(1) Create a VM](https://github.com/user-attachments/assets/a108536f-d5b8-4825-899f-5310d920a38e)

- Log into the VM with Remote Desktop
  <p>We'll use the Remote Desk Protocol program within our windows system to connect to our virtual machine. All you need it to copy the public IP Address from the virtual machine that we created, and paste it into the RDP program to initialize the connection. </p>
  
  ![VM IP ADDRESS](https://github.com/user-attachments/assets/281ffd5f-79dc-4c83-b048-4ca738fc1353)
![RDP Login](https://github.com/user-attachments/assets/ec17df63-df47-4d51-a2e4-a1cd1f9815f7)

  
- Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
  We will use the files in this folder to install osTicket and some of the dependencies. Make sure to actually unzip the folders contents onto your Virtual Machine, otherwise you may run into issues later.
  https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD


<h2>Installation Steps</h2>
- Step 1, Install / Enable IIS in Windows WITH CGI
We're going to install/enable IIS within windows with CGI enabled. To get to the IIS settings you need to navigate to the windows control panel and select programs. After selecting programs you need to select the 'Turn Windows features on or off' option, which will pull up the window which includes IIS and many other options.
  
![control panel, programs](https://github.com/user-attachments/assets/c15137ca-e54d-4e4e-af91-451b64cdd339)![Windows Features Breakdown](https://github.com/user-attachments/assets/f545e435-5f3e-424b-ad3e-22d39f01c354)


Within that window find ISS, and check the box. Make sure you actually check the box before expanding IIS for more features, otherwise there's potential for it to not show up when we are looking for it later on. Once it's expanded go ahead and go into the World Wide Web Services folder, and finally into the Application Development Features folder to find CGI. Make sure to select CGI before hitting Ok. That's the end of step one.</p>

- Step 2, From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- 
![PHP manager](https://github.com/user-attachments/assets/bf0071ab-e1c9-4c7b-8d1e-94af2e751d7b)

This step is pretty straightforward, you just need to go into the folder and select 'PHPManagerForIIS_V1.5.0.msi'. The installation for this program is very simple, you just click 'Next, select 'I Agree', and select 'Next' before closing out the window.

- Step 3, From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

Installing these modules is what is going to allow us to run and use osTicket, the installation for many of them is similar, and might feel a bit repetitive. But I assure you it is very necessary to have osTicket functioning properly within our Virtual Machine. Next is the Rewrite Module, within the same 'osTicket-Installation-Files' folder select the 'rewrite_amd64_en-US.msi' option.

![ReWriteModle](https://github.com/user-attachments/assets/7009612d-5a83-4f74-8b31-bb120b748b10)

Once It's opened checked the box agreeing to the terms in the Licesnse Agreement, and click install. It will take a second before prompting you with the option to 'Finish', concluding the installation process.

- Step 4, Create the directory C:\PHP

This step gives us a place to store our files in the upcoming step. You'll want to open up file explorer and navigate to 'This PC' then on to the local C drive 'Windows(C:)'. Here you'll want to create a new folder and name it 'PHP'.

![PHP --](https://github.com/user-attachments/assets/1eb84b17-e6da-48ed-b2dd-2e8d342a4a2a)

- Step 5, From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

Click on the 'php-7.3.8-nts-Win32-VC15-x86.zip' and select the extract button at the top of the file explorer. Once selected the 'Extract All' option should appear at the top of the file explorer. Select it and click the 'Browse' option. You'll want to navigate to the location of the PHP folder that we created in the last step and select that as the destination for the zipped contents before hitting 'Extract'.

![php extraction zipper](https://github.com/user-attachments/assets/18552a1e-6558-4cb6-88d1-eff8141b976f)

- Step 6, From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

Open up the 'osTicket-Installation-Files' folder and double click the VC_redist.x86.exe file. Check the box agreeing to the terms and conditions before selecting 'Install'. The setup should be successful and present you with the option to close the window.

![VCREDIST](https://github.com/user-attachments/assets/9638c7cb-4f63-4ff2-87b9-d7550edc3930)

- Step 7, From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

Open up the 'osTicket-Installation-Files' folder and double click the 'mysql-5.5.62-win32.msi' file. Once the instalation window has opened you'll want to hit 'Next', agree to the terms and conditions, and hit 'Next' again. The window will prompt you with the setup type, we'll go ahead and choose the typical setup before continuing on with the 'Next' button.

![MYSQL](https://github.com/user-attachments/assets/125d446e-f94f-4754-a6f7-e62f81e3f3bc)

Next you'll click on 'Install'. Once it's done click 'Finsih', and it will open the Server Instance Configuration Window. Select 'Next' and you'll be prompted with two options, detailed configuration and standard configuration. We're going to go ahead and select the standard configuration here before hitting 'Next'. You'll want to hit 'Next' one more time before you'll be prompted with the window where you decide what your SQL password will be. We'll use this password later on to link up our SQL database with the osTicket application, so make sure to note it somewhere accessible. Enter your password and proceed with 'Next'. The server instance should be ready to execute, select the 'Execute' option. It will execute the configuration before prompting you with the last window, just select 'Finish' to complete the process.

- Step 8, Open IIS as an Admin

In the bottom left search bar if you type IIS the Internet Information Services program should appear, make sure to run it as an administrator. Below is what it should look like once opened.

![Internet Information Services](https://github.com/user-attachments/assets/231eff41-0f62-42c9-80a0-ab20a8d15ca2)

- Step 9, Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Within the IIS program you'll want to select the PHP Manager option. Once it's opened, under PHP Setup you should see 'Register new PHP version' on the bottom left. You'll want to click on that, which will open up the window from which you'll select the path for the actual PHP executeable. Click on 'browse' and make you're way to the PHP folder we created earlier. Within that folder at the very bottom there should be the PHP executable, labeled as 'php-cgi'. Select that option and hit 'Ok'. You're PHP version should now be registered. 

![PHP MANGER](https://github.com/user-attachments/assets/84dc74d0-7d26-46e7-bd5d-3bbdded003c9)

- Step 10, Install osTicket v1.15.8

To install osTicket we need to go into the 'osTicket-Installation-Files' folder and unzip the 'osTicket-v1.15.8.zip' folder onto your desktop. Afterwards we need to go into that folder and copy the 'upload' folder from it's contents. We're going to paste the 'upload' folder that we copied into the directory 'c:\inetpub\wwwroot', and rename it from 'upload' to 'osTicket'. Make sure it's correctly named osTicket, otherwise the system will have issues trying to find the folder when searching for it in the future.

![upload rename](https://github.com/user-attachments/assets/ab160244-5aa3-43ce-b648-6821894aceef)
![osticketupdated vestion](https://github.com/user-attachments/assets/9e4598fd-8185-4d45-ac43-5fe5bc2098ab)

- Step 11, Open osTicket through IIS

If you already had IIS open, you'll want to close the application and reload it. Next you'll want to and click 'Stop', and then 'Start' from the options in the top right hand corner of the IIS window to allow the system to restart itself. Next you should be able to open the osTicket application by following the dropdown menus on the left hand side of the IIS application until you get to the osTicket folder.

![dropdownmenus](https://github.com/user-attachments/assets/642c3129-843d-4f86-a55f-2bd763b89755)

Once you reach the osTicket folder, click the folder, and on the right hand side you'll want to select the browse '*:80 (http)' option under 'Browse Folder'. If you did everything correctly the osTicket install window should appear in a windows browser as seen below.

![osticketinstaller](https://github.com/user-attachments/assets/c680a63f-e2f8-40c6-bced-1ef02a064e4f)

- Step 12, Enable some extensions that aren't already enabled

We're going to go back into IIS and follow the dropwdown path that we followed previously until we get back to the osTicket folder. Once selected we're going to double click on PHP Manager, and then click on 'Enable or disable an extension'. Within that list there's 3 extensions that we are going to enable.
- php_imap.dll
- php_intl.dll
- php_opcache.dll
After enabling the extensions you can refresh the window browser that holds our osTicket installation page to observe the changes on screen.

![updatedextensions](https://github.com/user-attachments/assets/9dfce69b-25a3-459e-900a-f63c363030dd)

- Step 13, We're going to rename a PHP file and assign permissions to the file within the osTicket folder that we renamed earlier.

Within the directory 'C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php' rename the 'ost-sampleconfig.php' file to 'ost-config.php'.

![ostconfig](https://github.com/user-attachments/assets/2e712147-b215-4f90-a834-3ce99c5877cf)

Then we're going to change the permissions on the file. Right click it and select Properties > Security > Advanced. Within the advanced security settings click on disable inheritance in the bottom left. It will ask you what you want to do with the current permissions, go ahead and disable all of them. After getting rid of the permissions you'll want to click add in the bottom left, select 'Select a principal' from the top of the window.

![permissions](https://github.com/user-attachments/assets/5fa73550-459c-4562-a730-134a5ab67cf3)

For the User or Group you'll want to type in 'everyone' and assign full control. Once done you can hit apply, and close out the window after hitting ok.

- Step 14, Continue setting up osTicket in the browser

![Settings section](https://github.com/user-attachments/assets/e73e9088-7a3a-4017-a240-5a2259539665)

Under the System Settings, the Helpdesk name can be whatever you want, for example 'CompanyEx Help Desk'. The email is the destination for customer sent emails. If you're doing the setup and installation process as a form of training these matter less. Part of the Admin User information will be used to sign into the osTicket system later on as an admin, so it's important to record the username and password that you enter for these for future use. The database settings will be filled out here in the near future, so there's no need to worry about them for now.

- Step 15, Install HeidiSQL and create a database

The next step is to install our SQL database, necessary for the background storing of information within the osTicket application. From the “osTicket-Installation-Files” we're going to doouble click on the Heidi SQL. You'll initially be prompted with a license agreement, hit 'accept' and continue on with 'next'. The next screen will ask you to choose the installation location for the program, this can be left as default. You'll want to go through the next 3 windows hitting 'next' until you're able to hit 'finish' and 'install'. Once HeidiSQL finishes installing and opens, we're going to create our database. Hit the 'New' green plus button on the bottom left.

![HeidiSQL](https://github.com/user-attachments/assets/a32da6f7-04d1-4c7e-b0a6-12c0d12620e6)

Here you'll be prompted to enter the password which we previously used when installing and setting up MySQL in step 7. Enter the password you used and click on 'open'. Now we can go ahead and create our database. You'll want to right click on the bold 'Unamed' header at the top, go down to 'Create New', and click on 'Database'. The name for the database must be 'osTicket', otherwise the system will have trouble trying to integrate osTicket and SQL. After finishing that step we can return to our osTicket setup page.

- Step 16, Finish Setting up osTicket within the browser

We'll finish out the osTicket browser setup by filling out the information at the bottom under 'Database Settings'. For the database name we need to make it match what we typed in earlier into the SQL database, so we'll want to enter 'osTicket' here. The password and username also needs to match what we entered during the SQL setup steps. I left the password and username as 'root' for simplicity sake, so that's what I enter during this step. 

![database settings](https://github.com/user-attachments/assets/7bd4b686-9b97-417e-9e61-409863810d22)

Once completed we can go ahead and click on install. If there were no errors made in any of the previous steps we should reach a congratulations page within the osTicket browser and be completed with the osTicket installation process!

![congratulations](https://github.com/user-attachments/assets/68d59f04-31ee-4cab-9990-373e9aec6882)

At the bottom of the page there are two links for you to use, one is a link for end users to go in and make tickets for any current problems they may be experiencing, and the other is a link for admins and helpdesk employees to log in to work those said tickets.


<br />
