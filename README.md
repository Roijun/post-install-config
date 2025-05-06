<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Installation Setup and Configuration.</h1>
<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- osTicket

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Have the osTicket software successsfully installed onto a virtual machine from my previous step by step walkthrough. 
 
<h2>Overview</h2>

In this walkthrough we're going to explore the osTicket portal a bit and make some configurations to set us up for creating and solving some mock tickets for the third and final walkthrough within the osTicket software. 

<h2>Setup and Configuration</h2>

- Roles

Roles are a way to group permissions together and give permissions to certain people. We're going to configure a new role and name it SupremeAdmin. To navigate to the roles section you'll want to first log in via the Admin link that was provided at the congratulations section. Once there use your username and password that we set in the previous walkthrough to log in to osTicket. Once you've logged in you'll be presented with the landing page, as presented below. 

![osticket landing](https://github.com/user-attachments/assets/461846e7-7fef-40ee-b42a-f2cb084d1ee5)

First we need to navigate to the admin panel, which is located in the top right. Once there you'll want to click on 'Agents' located on the far right of the top most row. 

![roles](https://github.com/user-attachments/assets/033634a0-be6e-44cc-995e-eacb54f1f314)

Once you've arrived at that page make sure to click on the 'Roles' option inside the second row from the top. Once there create a new role and name it SupremeAdmin. For the permissions section there are 3 different choices. Tickets, Tasks, and Knowledge base. For supreme admin we'll want to go through each of them and check each box to allow access and control to our new role. Once you're done assigning permissions you can finish out by clicking add role at the bottom. 

- Departments

Next we'll be taking a look at departments. Departments allow use to set ticket visibility to large sections of agents. For example you might want your system admin department to be able to see all of the avialble tickets, while only allowing the financial department to see finance related help tickets. You should be able to find the departmets section from the page you previously had navigated to near the top of the screen. We're going to click on that button to configure a new department. 

![departments](https://github.com/user-attachments/assets/d99f1300-619d-498f-b7b1-fc70f3ad2085)

Once at this page just click on 'Add new department' on the right hand side of the screen. There's lots of settings you could configure to tweak your departments to whatever your needs may be. There's also the access tab where ou can assign agents to the department as you're creating it. We don't have any agents in our osTicket system currently, so we'll be doing this later. So you can go ahead and hit create department down at the bottom of the page. 

- Teams

Teams are useful if you want to create a group of people who are all from different departments. An example might consist of the SysAdmins who are responsible for an online banking system, as well as the some help desk employees who are responsible for working the tickets within that area. Teams should be very straightforward to navigate to from where we left off. Just click on 'Teams' at the top of the page. Then select 'Add New Team' on the right hand side. 

![teams](https://github.com/user-attachments/assets/73b9bd51-ae9c-48ae-aa29-21b2fbc9ebc2)

Teams are pretty straightforward, as there's not much to configure here. We're gonna give our new team the name 'online banking'. If we had any users at this point we could add them to the new team within the 'Members' tab through the menu, but since we don't we're just gonna go ahead create the new team as is. 

Before we configure some agents for our walkthrough we're going to make sure that unregistered users can create tickets within our system. Since we're already in the admin panel, all we should need to do is navigate to 'Settings' and then click on 'Users'. Under authentication settings make sure that the 'Require Registration' box is unchecked.

![registration](https://github.com/user-attachments/assets/5816b27e-3f77-4613-b399-186a711cac8a)

- Agents

Agents are the actual individuals who get hired as Help Desk employees to work and solve the tickets created when people are having IT related issues. We configure agents from the admin panel, which we should already be in after checking our registration settings. We'll just select 'Agents' fron the row closest to the top of the page. 




<br />
