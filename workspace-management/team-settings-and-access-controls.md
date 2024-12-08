# Team Settings & Access Controls

A MindStudio Workspace has different **Roles and Access Controls** to manage collaboration and sharing within your workspace. Whether assigning workspace-wide roles or sharing access to individual AI Workers, you can ensure every user has the right level of permissions for their responsibilities. This guide explains the available roles and access controls in MindStudio.

## Team Settings

Workspace roles define access levels for managing both the workspace and its AI Workers. These roles are designed to support various levels of responsibility, from contributors to administrators.

***

### **Inviting People to Your Workspace**

Inviting people to your workspace in MindStudio is simple and ensures your team members have the correct roles for effective collaboration.

1. Navigate to the **Team** section of your workspace.
2. **Click the Invite Button i**n the top-right corner
3. **Enter the Email Address** of the person you want to invite in the provided field.
4. **Select the Role** by using the Role dropdown menu.
5. **Click Add Button** to send the invitation.

***

### **Workspace Role Quick Reference Table**

<table data-full-width="false"><thead><tr><th width="149">Role</th><th>View AI Workers?</th><th>Edit AI Workers?</th><th>Manage Users? </th><th>Access Workspace Settings</th></tr></thead><tbody><tr><td><strong>Owner</strong></td><td>All</td><td>All</td><td>All</td><td>Yes</td></tr><tr><td><strong>Admin</strong></td><td>All</td><td>All</td><td>All (except Owners)</td><td>Yes</td></tr><tr><td><strong>Member</strong></td><td>All</td><td>Only their own</td><td>No</td><td>No</td></tr><tr><td><strong>Guest</strong></td><td>Invite Only</td><td>Invite Only</td><td>No</td><td>No</td></tr></tbody></table>

***

### **Managing Guest Access to AI Workers**

On the **Team Page**, you can manage the permissions of guests for specific AI Workers, allowing you to adjust their access levels or remove access as needed.

1. Navigate to the **Team Page** of your workspace. Then find the guest whose access you want to manage in the list.
2. **Click Manage Button** to open the **Manage User Access** modal.
3. **Adjust Access Levels**
   * Review the AI Workers the guest has access to, listed in the modal.
   * Use the dropdown next to each AI Worker to update the access level:
     * **Use Only**: Limits the guest to viewing and using the AI Worker.
     * **Edit Access**: Allows the guest to edit the AI Worker.
4. (optional) To **remove the guest** entirely, click the red trash icon next to their role.

***

### **Upgrading and Downgrading Team Roles**

1. Navigate to the **Team Page** of your workspace. Locate the list of team members.
2. Find the Member to who’s role you’d like to modify
3. Use the dropdown menu next to the user’s current role to select a new role. Changes are applied immediately after selecting the new role.

***

### Team Role Types

#### **Member**

The **Member** role is ideal for contributors who create and collaborate within the workspace but do not need administrative permissions.

**Capabilities**:

* Create new AI Workers.
* View all AI Workers in the workspace, including those they did not create.
* Invite Guests to view and edit AI Workers that they create.

**Restrictions**:

* Cannot edit AI Workers created by others unless explicitly invited.
* Cannot share Edit Access for AI Workers they do not own.
* Cannot access any workspace settings pages including:

#### **Admin**

The **Admin** role allows for broader workspace management, including user and workspace settings management, without full ownership authority.

**Capabilities**:

* View and edit all AI Workers.
* Access and modify all workspace settings.
* Invite and manage Admins, Members, and Guests.
* Downgrade or remove Admins, Members, and Guests.

**Restrictions**:

* Cannot remove or downgrade Owners.

#### **Owner**

The **Owner** role has complete control of a workspace.

**Capabilities**:

* View and edit all AI Workers.
* Access and modify all workspace settings.
* Invite and assign any role (Owners, Admins, Members, Guests).
* Downgrade or remove any role (Owners, Admins, Members, Guests).

***

## **AI Worker Access Controls**

MindStudio also provides controls for granting Guest access to specific AI Workers without workspace-wide permissions.

### Sharing an AI Worker

You can add new guests with specific permissions using the **Sharing & Access Controls** modal. Here’s how to do it:

1. Open the AI Worker you want to share.
2. Click the **Share** button to bring up the **Sharing & Access Controls** modal.

#### **Inviting a Guest**

1. **Enter the Guest’s Email**
   * In the text box labeled "Enter email address," type the guest’s email address.
2. **Click Invite**
   * Once the email is entered and the access level selected, click the **Invite** button.
3. **Choose a Permission Level**
   * Select the desired access level from the dropdown menu:
     * **Edit Access**: Allows the guest to edit the AI Worker.
     * **Use Only**: Limits the guest to viewing and using the AI Worker without editing.
4. **Optional: Generate an Invite Link**
   * Use the **Invite Link** section to generate a sharable link for the guest.
   * The default access level for the link can be set to **Use Only** or **Edit Access** using the dropdown menu.
   * Click **Copy** to share the link.

***

#### **Managing AI Worker Access**

Once guests are added, their details appear in the modal under "People with Access."

* **Adjust Permissions:** Use the dropdown next to a guest’s name to change their access level between **Edit Access** and **Use Only**.
* **Remove Access:** Click the red trash icon to remove a guest’s access entirely.

***

### Access Control Types

#### **Use Only**

A Guest with **Use Only** access is designed for users who are intended to use the AI only.

**Capabilities**:

* View and use specific AI Workers they are invited to.
* View the workspace they are invited to.
* Guests can only see the specific AI Workers that they have been invited to.

**Restrictions**:

* Cannot edit AI Workers.
* Cannot view all AI Workers in the workspace.
* Cannot view editor controls.
* Cannot share links or manage permissions.
* Cannot access other AI Workers or workspace settings.

#### **Edit Access**

A Guest with **Edit Access** role allows for collaborative editing of specific AI Workers without granting workspace-wide access.

**Capabilities**:

* Edit AI Workers they are explicitly invited to.
* View editor controls for the invited AI Workers.
* Guests can only see the specific AI Workers that they have been invited to.

**Restrictions**:

* Cannot view or access workspace settings.
* Cannot edit or access AI Workers they have not been invited to.
* Cannot invite or manage other users.
* Cannot share links or manage permissions.
* Cannot access other AI Workers or workspace settings.
