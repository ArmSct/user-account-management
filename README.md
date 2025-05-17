

# Managing User Accounts in Active Directory
This project demonstrates configuring Group Policy to enforce lockout thresholds, triggering account lockouts through failed login attempts, unlocking and resetting accounts, enabling/disabling users, and reviewing event logs on both the domain controller and client machine. A domain controller (DC-1) and client (Client-1) virtual machine are pre-configured for this lab.

## Technologies Utlizied
- Microsoft Azure
- Windows Server
- Windows 10 
- Active Directory
- Group Policy Management
- Event Viewer
- Remote Desktop (RDP)

## Actions and Observations

### Account Lockouts 
Log in to the Domain Controller (DC-1) and open Active Directory Users and Computers. Create a Default Domain Policy that locks out users after 5 failed login attempts. 

![mstsc_VvMKquuZzG](https://github.com/user-attachments/assets/956800aa-1a4b-4dae-990e-ff37093dfc88)

![mstsc_rbmxmvm1qQ](https://github.com/user-attachments/assets/5adf62e7-408d-4aeb-b7ea-2e03ca1ef6da)

On the client machine,  attempt to log in with this user account 5 times with an incorrect password. This will result in the account being locked.

![CredentialUIBroker_50J3ENrGNl](https://github.com/user-attachments/assets/4e7a6a4e-5f7e-4de9-83c3-96d03f29dbf0)

![mstsc_91zsPqfPCX](https://github.com/user-attachments/assets/3b15823c-dc10-40ab-af46-e49d3aa49845)

On the domain controller, open Active Directory Users and Computers. Search for the user's account name. Click on the user and check the unlock account box and click OK.

![mstsc_waVfQypH45](https://github.com/user-attachments/assets/bc1ab88d-1dc8-438f-a5fe-9502fcac4af0)

![mstsc_knmKYIcVq2](https://github.com/user-attachments/assets/81cbf46b-ce2a-493d-a00f-9551c3f6ec4b)

Confirm that the account has been unlocked by logging in as the user on the client machine.

![mstsc_CbMWABJDk2](https://github.com/user-attachments/assets/d001a246-2d2e-4a30-a4fa-59b0074936e5)


### Enable/Disable User Accounts

In ADUC, right-click the user account and disable their account. 

![mstsc_GTFT05qLMg](https://github.com/user-attachments/assets/0e5400a0-88e0-4139-8d56-3f19b6cb257f)

Attempt to log in from the client. You will receive an error ("The logon attempt failed") indicating the account is disabled. 

![CredentialUIBroker_8HGEd1AjBN](https://github.com/user-attachments/assets/f2ad3949-7f54-48fa-9c66-8f4eb0a4ac24)

On the domain controller, re-enable the account. As the client, test logging in again with the correct credentials.

![mstsc_pWMZJeljXs](https://github.com/user-attachments/assets/7d379169-ef9c-4a7c-b0e9-5f341b95512c)

![Uploading mstsc_1tEAKj7tVF.png…]()

### Observing Logs


