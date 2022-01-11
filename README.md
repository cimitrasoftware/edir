**Cimitra's eDirectory Practice**
**30 Common Actions For eDirectory Accounts**

![edir_practice_main_screen](https://user-images.githubusercontent.com/55113746/123368617-5c1a1f00-d539-11eb-842e-4010b50c7bc3.JPG)

**Cimitra's eDirectory Practice**

Cimitra's eDirectory Practice is on Bash script which allows for dozens of modifications you can make to eDirectory User accounts. For example, you can create a user in eDirectory, and set several of their attributes at the time of the user creation event.

Or you can modify only one or some attributes of an existing eDirectory User account.

# INSTALL CIMITRA EDIRECTORY PRACTICE SCRIPT

1. In a terminal on a Linux server, most likely a SUSE Server with eDirectory installed

2. Install the Cimitra's eDirectory Script with the command below:

    **curl -fsSL https://git.io/Jc5Yj | sh **

3. Go to the directory /var/opt/cimitra/scritps/edir

    **cd /var/opt/cimitra/scritps/edir**

4. **Run** the script as follows: ./cimitra_edir.sh**

# CONFIGURE CIMITRA EDIRECTORY PRACTICE SCRIPT SETTINGS FILE

1. **Edit** the **settings_edir.cfg** file with the settings needed to authenticate to your eDirectory tree via LDAP
\
***NOTE:*** If you don't want to use an already established Admin Level eDirectory account read the section below titled:  
**"[ CREATING A CIMITRA EDIRECTORY ADMIN ACCOUNT ]"**
\

    (a.) Fill in the settings config file, make sure that you at least fill in:

   **EDIR_AUTH_STRING**

   **EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_ADDRESS_ONE** 

   **EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_PORT_ONE**

   **EDIR_USER**

   ***[Example]***

       EDIR_AUTH_STRING="YouLetC1m1tra1n"
       EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_ADDRESS_ONE="192.168.1.53"
       EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_PORT_ONE="389"
       EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_ADDRESS_TWO="192.168.1.54"
       EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_PORT_TWO="389"
       EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_ADDRESS_THREE="192.168.1.54"
       EDIR_LDAP_SERVICE_SIMPLE_AUTHENTICATION_PORT_THREE="389"
       EDIR_USER="cn=cimitra_admin,o=edir_o"
       EDIR_EXCLUDE_GROUP=""

**TEST YOUR SETTINGS**

To do a **quick test** to see if everything is configured correctly, then run the Cimitra eDirectory Practice script as follows: 

*Run:* ./cimitra_edir.sh -Action "[some action]"
  
*EXAMPLE:*  **./cimitra_edir.sh -Action "ListAllUsersInTree"**

-OR-

*EXAMPLE:*  **./cimitra_edir.sh -Action "ListUsersInContext" -Context "ou=users,o=edir_o"**

***NOTE: There is no need to proceed until you have actually gotten a test to work!***
  
**[ CREATING A CIMITRA EDIRECTORY ADMIN ACCOUNT ]**

***NOTE: Follow this section if you intend to make a "Cimitra Admin" account rather than using an already established Admin-level eDirectory account***

1. Create a new user in eDirectory specific to cimitra, *Example:* cimitra_admin.edir_o

2. Give the cimitra_admin user the following rights: 

(a.) eDirectory Trustee rights within contexts to be administered within Cimitra

 iManager | Roles and Tasks | Rights | Modify Trustees | Object Name 
 
  - Choose a Context users that will be administered within Cimitra
  - Add Trustee
  - Choose the Cimitra Admin, *Example:* cimitra_admin.edir_o
  - Choose **Assigned Rights**
  - Select **Supervisor** for both [All Attributes Rights] & [Entry Rights]
  - Select **Done** | **Apply**

Repeat step (a.) for each context with users that will be administered within Cimitra

(b.) eDirectory Trustee rights to Root organization of the tree (don't worry, no admin rights needed here)

 iManager | Roles and Tasks | Rights | Modify Trustees | Object Name 
  - Choose a Root context of the tree
  - Add Trustee
  - Choose the Cimitra Admin, Example: cimitra_admin.edir_o
  - Choose **Assigned Rights**
  - Select **Read** and **Inherit** for [All Attributes Rights] 
  - Select **Done** | **Apply**

Edit the Cimitra eDirectory Practice Settings File: 

/var/opt/cimitra/scritps/edir/settings_edir.cfg

Update the following two settings: 

*Example*

**EDIR_USER="cn=cimitra_admin,o=edir_o"**
**EDIR_AUTH_STRING="YouLetC1m1tra1n"**

**[READ AND FOLLOW THIS DOCUMENT - Instructions for importing Cimitra Pre-Made Actions](https://github.com/cimitrasoftware/edir/blob/main/edir_import_instructions.pdf)**

**NOTE: Make sure to download the PDF file so you can use the Copy and Paste feature**

**[ WHAT THIS SCRIPT CAN DO ]**

Here are the actions you can take with this script.

1. Add User to eDirectory
2. Rename eDirectory User's SamAccountName
3. Change eDirectory User's First Name
4. Change eDirectory User's Last Name
5. Modify eDirectory User's Mobile Phone Number
6. Modify eDirectory User's Office Phone Number
7. Modify eDirectory User's Title
8. Modify eDirectory User's Description
9. Modify eDirectory User's Manager
10. Modify eDirectory User's Department
11. Add an eDirectory User to an eDirectory Group
12. Add an expiration date to an eDirectory User account
13. Remove the expiration date from an eDirectory User account
14. Enable an eDirectory User account
15. Disable an eDirectory User account
16. Lock an eDirectory User account
17. Unlock an eDirectory User account
18. Change the Password on an eDirectory User account
19. Get a report of several attributes on an eDirectory User account
20. Find all information about an eDirectory Group
21. List all users in an eDirectory tree
22. List all Users in a certain context in an eDirectory tree
23. Remove an eDirectory User from an eDirectory Group
24. Search for a user object, choosing attributes of the user, for example, their phone number with the full phone number specified: 801-555-1212
25. Wildcard Search for a user object, choosing partial attributes of the user, for example, search for their their phone number with: 801-555
26. Create an eDirectory Group
27. Report on eDirectory Groups in an OU
28. List eDirectory Group Membership
29. Add users to an eDirectory Group
30. Bulk add users to an eDirectory Group
 
 
 **[ IMPORTING ACTIONS INTO CIMITRA THAT USE THE CIMITRA EDIRECTORY PRACTICE SCRIPT ]**
 
 ** Importing Into Your Cimitra System**
 
 **IMPORT (Looping Animated GIF)**
 
![import_create_user](https://user-images.githubusercontent.com/55113746/123369537-2bd38000-d53b-11eb-8fb3-248cda30fd2b.gif)



