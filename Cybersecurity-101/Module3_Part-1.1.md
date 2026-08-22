## Windows Fundamentals 1 (contd)
The Windows folder ( C:\Windows ) is traditionally known as the folder which contains the Windows OS. The folder doesn't have to reside in the C drive necessarily. It can reside in any other drive and technically can reside in a different folder.**The system  environment variable for the Windows directory is %windir%**.

- Environment variables store information about the OS environment. This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders. One of the folders is System32.

- The System32 folder holds the important files that are critical for the operating system.Accidentally deleting any files or folders within System32 can render the Windows OS inoperational.

### User Accounts, Profiles & Permissions
User accounts can be of 2 types on a typical local windows system: **Administrator** & **Standard User.**

- An Administrator can make changes to system: add & delete users,modify groups,modify settings on the system,etc.
- A Standard User can only make changes to folders/files attributed to the user & can't perform system-level changes, such as install programs.

## Windows User Accounts and Groups

### User Accounts

* The **Administrator** can view and manage user accounts on the system.
* To view accounts:

  1. Open the **Start Menu**.
  2. Search for **Other User**.
  3. Open **System Settings → Other users**.
* An Administrator can select a local account and:

  * **Change account type**
  * **Remove** the account
  * **Add someone else to this PC**
* A **Standard User** does not have the option to add another user to the PC.

## User Profiles

* When a user account is created, a **user profile** is created when the user logs in for the first time.
* User profiles are stored under:
  `C:\Users`
* Example:
  `C:\Users\Max`
* The **User Profile Service** creates the profile during the user's first login.
* Common folders in a user profile include:

  * **Desktop**
  * **Documents**
  * **Downloads**
  * **Music**
  * **Pictures**

## Local Users and Groups

* Windows provides **Local Users and Groups Management** to manage local accounts and groups.
* Open it by:

  1. Right-click **Start Menu**.
  2. Select **Run**.
  3. Type `lusrmgr.msc`
* It contains two main sections:

  * **Users** – Lists local user accounts.
  * **Groups** – Lists local groups and their descriptions.

## Groups and Permissions

* Groups have specific **permissions** assigned to them.
* Administrators can add users to groups.
* A user **inherits the permissions** of the groups they belong to.
* A user can belong to **multiple groups**.

### Key Points

* User profiles are stored in **`C:\Users`**.
* `lusrmgr.msc` opens **Local Users and Groups**.
* **Groups simplify permission management**.
* Users inherit permissions from their assigned groups.
* Administrators have greater control over user accounts and groups.
