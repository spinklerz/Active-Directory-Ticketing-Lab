# Active-Directory-Ticketing-Lab
Setup a virtual network with a pfsense gateway, DC01, and a windows workstation to practice managing user accounts, setting up GPOs and an ubuntu machine that manages a ticketing system.

## Topology 

![Network Topology](./images/Network%20Topology.png)

## Overview
 - Deployed an Active Directory environment within vmware on a virtual network with an Ubuntu osTicket system and a Windows 11 workstation under the domain name buisness.local.

 - Simulated a helpdesk ticket where user John would be locked out of his account on AD. John navigated to the local ticketing system domain and submitted a ticket. In which the admin responded to the ticket and reset the password on AD. Afterwards the AD admin verified that John was able to log in. 

 - Setup Microsoft 365 business with user provisioning, shared mailboxes, distribution groups, and Conditional Access policies enforcing MFA across targeted applications with role-based permissions. 

- Machine verification

![Machine verification](./images/machine_veri.png)

 ## Scenario 1
 - John gets locked out of his AD account and submits a ticket on the local ticketing system. 

 1.) John gets locked out

 ![John locked out](./images/John_Invalid_Login.png)

 2.) John submits a ticket

 ![John Submits a ticket](./images/John_Request.png)

 3.) Help Desk notices a new ticket

  ![Ticket](./images/John_password_osticket.png)

 4.) Help Desk responds to the new ticket

 ![Ticket reply](./images/Ticketing%20system%20Reply.png)

 5.) AD admin resets Johns password

 ![Password Reset AD](./images/John%20Password%20Change.png)

 6.) Help Desk communicates with John in person or over the phone the temporary password. 

 ![Password reset](./images/Reset%20John's%20password.png)

 7.) Verifies John's login via powershell logs or eventviewer

 ![John login verification](./images/Proof%20of%20John%20Login%20from%20DC01.png)

 8.) Ticket Closed

 ![Closed Ticket](./images/Ticket_closed.png)

 ## Scenario 2
 - Setup an environment on microsoft entra and user john forgot his password and needs it reset. 

 1.) Password Reset
 ![John Base password reset entra](./images/Password%20reset.png)

 2.) Password Reset on John's end

 ![Password reset John Base](./images/Password%20reset2.png)

## Additional Actions Taken


- Created a security group giving the siem_admin admin access 

![Security Group](./images/admin_access.png)

- Browsed login audit logs

![audit logs](./images/Audit_logs.png)

- Browsed audit log in logs

![Login Logs](./images/login_logs.png)

- MFA enforcement Policy

![MFA enforcement](./images/MFA_Enforcement.png)

- MFA verification

![verification](./images/MFA_veri.png)

- ITS group creation

![group creation](./images/ITS_Group_Creation.png)

- Shared Mailbox Creation

![Shared Mailbox](./images/Mail_box.png)