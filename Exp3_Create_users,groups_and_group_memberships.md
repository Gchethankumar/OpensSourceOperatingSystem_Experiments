### AIM:
To create users, groups and group memberships.

### PROCEDURE:

#### 1.Creating a group

The first line [root@serverb ~]# groupadd admin creates a new group named admin. A group is a collection of users that can share certain permissions. The root user is the system administrator and has the authority to create groups.

#### 2.Adding users to the group 

The next three lines [root@serverb ~]# useradd -G admin harry, [root@serverb ~]# useradd -G admin natasha, and [root@serverb
~]# useradd -G admin sarah create three new user accounts named harry, natasha, and sarah. The useradd command is used to create new user accounts. 
The -G admin option adds the new user to the admin group that was previously created.

#### 3.Setting a restricted shell for a user

The line [root@serverb ~]# useradd -s /sbin/nologin sarah creates new user account named sarah.However, the -s /sbin/nologin option specifies that the user's shell is set to /sbin/nologin. This is a special shell that restricts the user from logging
into the system using a standard login method. Users with this shell can only be granted access through special means.

#### 4.Changing passwords

The lines	[root@serverb ~]# passwd repeated three times initiates a password change for the users harry,natasha , and sarah respectively. The passwd command is used to change a user's password.

Since the user executing the commands is root, they are able to change passwords for other users on the system. In a normal user account scenario, you would only be able to change your own password using this command.

The text following	passwd: prompts the user for the new password. For security purposes, the
characters typed are not shown on the screen.

#### 5.Verifying password change

The line stdin harry(and similarly for natasha and sarah) shows that the user has successfully entered a new password.
The line all the authentication tokens updated sucessfully.following each password change indicates that the system has updated all login credentials associated with the user account.

### OUTPUT

![Picture1](https://github.com/user-attachments/assets/f11a26b4-0dc0-4d1a-b7b1-8458a1045d97)

### RESULT:

Thus the users and groups are created successfully.
