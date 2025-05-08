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

- Have the osTicket software successsfully installed onto a virtual machine from my previous osTicket walkthrough. 
 
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

Agents are the actual individuals who get hired as Help Desk employees to work and solve the tickets created when people are having IT related issues. We configure agents from the admin panel, which we should already be in after checking our registration settings. We'll just select 'Agents' fron the row closest to the top of the page. Once here we're going to want to click 'Add New Agent' from the top right. I'm going to make it simple and call our new agent here Jane. We're going to use Jane later on to work some mock ticketes, so I'm going to set her username and password and record them on my computers notepad for future use. 

![newagent](https://github.com/user-attachments/assets/83dd8e6c-c215-41b8-9f0c-a81985658d29)

I'm going to make Jane apart of the SysAdmin department, and add her to the Supreme Admin role. I'm also going to assign her to the online banking team through the team tab as well. Once we're done configuring Jane we'll hit 'Create' at the bottom of the page to finalize our decision. Before finishing off with the agent section we'll want to create one more agent. We'll call our second agent John, and add him to the support department. We'll also select his role as 'All Access', we can leave the permissions and team sections alone before continuing on with creating our new agent.

![Jane](https://github.com/user-attachments/assets/c23cdcf7-9bfd-4559-b952-4254f74b3062)

- Users

Users are the actual customers who will be submitting tickets to the helpdesk. You don't need to be a user to create a ticket since we changed the authentication settings, but it helps to keep track of the individuals who are actually experiencing issues. To create a user we need to click on the 'Agent Panel' in the rop right, before clicking on the 'Users' tab. Once you've arrived click on the 'Add User' on the right side of the screen. Users only really require an email and a username, and we're going to record these in our notepad as well for future use. We're going to name our user Karen, and give her a fitting email to match.

![create asuser](https://github.com/user-attachments/assets/c18172ac-4c85-4ca5-9899-ad94b313e7b2)

- Service Level Agreements (SLA's)

Service Level Agreements allow us a way to organize tickets based on severity, and also come with a time requirement for how long you have before responding to the ticket. We're going to go ahead and configure a few SLA's. To navigate to the page we're going to want to click on 'Admin Panel' in the top right. Once here we'll want to navigate to the manage tab, where you'll see SLA as an option near the top of the screen. Select SLA, and then select 'Add New SLA Plan'. 

![SLA](https://github.com/user-attachments/assets/f2c0ce3f-9695-4df0-be9c-acf92e5e35ac)

We're going to create 3 different SLA's. The first will be labeled Sev-A, we're going to give it a grace period of 1 hour, and set the schedulue to 24/7 before hitting 'Add Plan'. The second SLA will be labeled Sev-B, and we'll be giving it a grace period of 4 hours, and a schedulue of 24/7. The final SLA will be labeled Sev-C, and we'll set this grace period to 8 hours with a schedulue set to buisness hours, Monday-Friday.

- Help Topics

The final section we'll be covering is help topics. Help topics are a way to catagorize the help tickets that are incoming, so that the appropriate agents can respond appropriately. We can access them from the admin panel inside the manage tab, which we should already be positioned in after creating our SLA's. Click on the 'Help Topics' tab. Then we're going to select 'Add New Help Topic' in the top right hand corner. We're going to be adding a few help topics so we can use them later on in the following addition to this walkthrough. We'll start by adding our first help topic, which we'll name 'Business Critical Outage'. For the parent topic we'll go ahead andd make it apart of 'Report a Problem' before hitting 'Add Topic' there at the bottom. Parent topics are a way for us to narrow down what type of issue we're dealing with.

![bca](https://github.com/user-attachments/assets/8dac8228-ec48-45ad-b20d-5332e756ece3)

The next topic we're going to add will be labeled as 'Personal Computer Issues' and it will also be under the 'Report a Problem' parent topic. The third topic we'll add will be labeled 'Equipment Request', and we'll put this under the 'General Inquiry' parent topic. We're only going to add two more before we're done with this section. The next topic will be named 'Password Reset' and it will reside in the 'Report a Problem' parent topic. The final help topic we'll be creating will be named 'Other' and we'll keep it under the 'General Inquiry' parent topic. Now we should have a list of all the help topics we created.

![Helptopicsoverview](https://github.com/user-attachments/assets/353d048d-6e0f-45f2-aa64-725bf1f1a202)

This marks the end of this page's walkthrough. We've completed a general inital setup of osTicket, going through the variety of avaialble configurations inside roles, departments, teams, agents, users, and SLA's. The intial setup helps guide us through the osTicket system and allows us to get a better understanding of how things work. In the next section on osTicket we'll be going through creating and solving some mock tickets, allowing us to get a more in depth view on how the ticketing system works, and how to solve tickets as an agent working to assist those in need. 






<br />
