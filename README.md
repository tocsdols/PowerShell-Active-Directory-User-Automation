# PowerShell Active Directory User Automation
PowerShell script for automated Active Directory user creation, password generation, and OU assignment in a Windows Server environment.

## Overview

This project demonstrates how to automate Active Directory user provisioning using PowerShell. The script accepts user information as parameters and automatically creates a new Active Directory user account within a specified Organizational Unit (OU).

The script was developed as part of my Active Directory administration and PowerShell automation lab running on Windows Server in a Microsoft Azure environment.

## Project Objectives

The goal of this project is to:

* Reduce the time required to manually create Active Directory users.
* Standardize the user creation process.
* Demonstrate PowerShell automation for system administration tasks.
* Improve efficiency in Active Directory account provisioning.

## Technologies Used

* PowerShell
* Active Directory Domain Services (AD DS)
* Windows Server
* Microsoft Azure
* Active Directory Users and Computers (ADUC)

## Features

The script performs the following actions:

* Accepts user details through command-line parameters.
* Generates a random password automatically.
* Converts the generated password into a Secure String.
* Creates a new Active Directory user account.
* Assigns the user to a specified Organizational Unit (OU).
* Enables the account upon creation.
* Creates a User Principal Name (UPN).
* Forces the user to change their password at first login.

## Parameters

| Parameter | Description                |
| --------- | -------------------------- |
| Firstname | User's first name          |
| Surname   | User's last name           |
| Username  | Active Directory username  |
| OU        | Target Organizational Unit |
| Domain    | Domain name                |

## Script Workflow

### Step 1: Collect User Information

The script prompts for:

* First Name
* Surname
* Username
* Organizational Unit
* Domain Name

### Step 2: Generate Password

A random 12-character password is automatically generated using:

* Numbers
* Uppercase letters
* Lowercase letters

### Step 3: Convert Password to Secure String

The generated password is converted into a SecureString object for use with Active Directory account creation.

### Step 4: Create Active Directory User

The script uses the `New-ADUser` cmdlet to:

* Create the account
* Configure account properties
* Set the password
* Enable the account

### Step 5: Assign Organizational Unit

The new account is automatically placed inside the specified Organizational Unit (OU).

### Step 6: Enforce Password Change

The user is required to change the generated password during their first login.

## Example Usage

```powershell
.\Create-ADUser.ps1 `
-Firstname "Samuel" `
-Surname "Okonji" `
-Username "sokonji" `
-OU "Engineering" `
-Domain "BENX.local"
```

## Example Output

```text
Password Generated as : hD7kL9pQ2xW1
```

The script then creates the user account and places it inside the specified Organizational Unit.

## Screenshots

### Script Execution

<img width="1470" height="956" alt="image" src="https://github.com/user-attachments/assets/bd2b0d78-46d4-4520-970c-21b75f19884b" />


### Password Generation

<img width="1423" height="251" alt="image" src="https://github.com/user-attachments/assets/1700a3bf-0c59-49a8-a69d-4a52ef36b1ce" />


### User Created in Active Directory

<img width="1469" height="929" alt="image" src="https://github.com/user-attachments/assets/a0131e6b-e64b-4f17-a949-99f41fd98a11" />



### User Properties

<img width="1394" height="312" alt="image" src="https://github.com/user-attachments/assets/7e3fe418-7aac-4dff-8354-d23ce53f1bd2" />


### Video Link
https://youtu.be/vJ0NgFGD79w


## Skills Demonstrated

* Active Directory Administration
* User Account Provisioning
* PowerShell Scripting
* Windows Server Administration
* Identity and Access Management (IAM)
* Microsoft Azure Administration
* IT Automation

## Future Improvements

Potential enhancements include:

* Bulk user creation from CSV files
* Automatic group assignment
* Email address generation
* Logging and audit reports
* Error handling and validation
* Password complexity customization


