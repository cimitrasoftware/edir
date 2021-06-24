# edir
Cimitra's eDirectory Practice

25 Common Actions For eDirectory Accounts

This script allows for dozens of modifications you can make to eDirectory User accounts. For example, you can create a user in eDirectory, and set several of their attributes at the time of the user creation event.

Or you can modify only one or some attributes of an existing eDirectory User account.

[ INSTALL ]

1. In a terminal on a Linux server, most likely a SUSE Server with eDirectory installed

2. Install the Cimitra's eDirectory Script with the command below

curl -fsSL https://raw.githubusercontent.com/cimitrasoftware/edir/main/install.sh | sh

3. Go to the directory /var/opt/cimitra/scritps/edir

cd /var/opt/cimitra/scritps/edir

4. Run: ./cimitra_edir.sh

5. Edit the settings_edir.cfg file with variables needed to authenticate to your eDirectory tree via LDAP

6. Run: ./cimitra_edir.sh -Action "[some action]"
  
EXAMPLE: ./cimitra_edir.sh -Action "UserReport" -UserId "jdoe" -Context "ou=users,o=cimitra"
  
-OR- 
 
EXAMPLE: ./cimitra_edir.sh -Action "ListAllUsersInTree"

[ CREATING A CIMITRA ADMIN ACCOUNT ]

1. Create a new user in eDirectory specific to cimitra, Example: cimitra_admin

2. Give the cimitra_admin user Supervisor Trustee rights to 

(a.) eDirectory contexts to be administered

iManager | Roles and Tasks | Rights | Modify Trustees

3. 


[ WHAT THIS SCRIPT CAN DO ]

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
 
