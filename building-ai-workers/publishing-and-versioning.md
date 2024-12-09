---
description: Manage, track, and publish new versions of your AI Worker in MindStudio.
---

# Publishing & Versioning

**Publishing** is the last step in preparing an AI Worker for deployment. In this article, we’ll cover all of the AI Worker Settings you can configure before publishing your AI Worker.

## **Publishing an AI Worker**

Publishing creates a versioned release of your AI Worker, locking in its current configuration. Once published, this version becomes accessible to users and collaborators.

#### **Steps to Publish**

1. Review the AI Worker’s metadata and configuration for accuracy.
2. Click the **Publish** button in the top-right corner.
3. Open the current version of your AI Worker.

**Note:** Before publishing, ensure you've opened up the AI Worker Settings and verified all metadata fields are correctly configured. This includes checking the name, description, API function name, icons, usage limits, and sharing settings.

***

## AI Worker Settings

AI Worker Settings provide configuration options for customizing, controlling, and managing your AI Worker. These settings are organized into several key sections that allow you to define everything from adding basic metadata (like name and description) to usage limits and sharing permissions.

Properly configuring these settings is crucial for ensuring your AI Worker functions as intended and is accessible to the right users.

#### Accessing AI Worker Settings

1. Navigate to the **Explorer Tab** on the left.
2. Click on the Root File at the top of the Explorer Tab to open the AI Worker Settings

### **Details**

The **Details** tab under the **General** section allows you to define key metadata and identifiers for your AI Worker. Make sure AI Worker is properly named, described, and configured for external integration.

#### **Name**

Enter a clear and concise name for your AI Worker. This name is displayed throughout the MindStudio platform and in shared links.

#### **Short Description**

Provide a brief description of your AI Worker’s purpose and functionality. This helps collaborators and end-users understand its role at a glance.

#### **API Function Name (Optional)**

Specify a custom API function name if you plan to invoke the AI Worker programmatically via the MindStudio NPM package. This is particularly useful for integrating the AI Worker into larger systems.

#### **Worker ID**

A unique identifier automatically assigned to your AI Worker. This ID is used for backend and API integration purposes. Click the copy icon to copy the Worker ID for use in development or debugging.

***

### **Icons and Media**

The **Icons and Media** tab lets you customize the visual representation of your AI Worker, both within the platform and when shared externally. This section ensures your AI Worker is visually distinct and branded appropriately.

#### **App Icon**

Upload an image to serve as the primary icon for your AI Worker. This icon is displayed in the MindStudio interface and associated with the AI Worker in all contexts.

* **Recommended Size**: 500x500 pixels.
* **File Types Supported**: PNG, JPEG.

#### **Social Sharing Image**

Add an image to represent your AI Worker when it’s shared on social media platforms or messaging apps.

* **Recommended Size**: 1200x630 pixels.
* **File Types Supported**: PNG, JPEG.

***

### **Usage Limits Tab (General Section)**

The **Usage Limits** tab allows you to set financial and operational boundaries for your AI Worker and its users. This ensures that your AI Worker operates within defined budgets, avoiding unexpected costs or overuse.

#### **Monthly Worker Budget**

Set a maximum spending limit for the AI Worker in a calendar month. If the Worker exceeds this budget, it will be suspended until the next month.

* **Example:** Set this value to $100 to restrict the AI Worker’s operational costs to $100 per month.

#### **Monthly User Budget**

Define a spending cap for individual users interacting with the AI Worker. If a user exceeds this limit within a calendar month, their access will be suspended for that period.

* **Example:** Set this value to $10 to limit each user’s spending to $10 per month.

***

### **Sharing**

The **Sharing** tab allows you to configure how your AI Worker can be accessed and shared with others.

#### **Remixing**

When enabled, others can create a copy of your AI Worker and modify it to build their own version. **Remixing is enabled by default.**

**Note**: Enabling this setting makes your AI Worker publicly remixable by anyone.

#### **Password Protect**:

When enabled, restricts access to your AI Worker with a password. Only users with the correct password can interact with the Worker. Ideal for limiting access to specific teams or individuals.

***

### **Transfer**

The **Transfer** tab allows you to reassign ownership of an AI Worker to a different workspace. This is particularly useful when moving AI Workers between personal and organizational workspaces or consolidating assets under a specific team.

#### **Transfer Workspace**

Select the destination workspace to which the AI Worker will be transferred. Once an AI Worker has been transferred, this action cannot be undone.

**Note on Ownership**: Each AI Worker is tied to a workspace, and the selected workspace will assume ownership and be billed for its usage.

***

### **Versions**

The **Versions** tab provides a comprehensive history of your AI Worker’s lifecycle, allowing you to manage and track both drafts and published versions effectively.

#### **Published Versions**

Displays a list of all previously published versions, sorted chronologically.

**Metadata:**

* **Version Name**: Helps identify specific releases (e.g., Version #1, Version #2).
* **Publisher's Name**: Identifies who published the version.
* **Timestamp**: Shows the exact time of publication.
* **Change log:** AI generated list of changes

**Controls:**

* **Open**: Click to view the current published version of the AI Worker.
* **Restore Version:** Visible on hover. Replaces the live version with the selected version and deletes any changes made to the draft.

#### **Draft Versions**

Lists the current draft version under development. Any changes you make to your project before publishing a new version are saved to this draft.

* **Delete Draft**: Removes all changes made to the current draft and restores settings to current published version.

#### **Version Statuses**

* **Drafts (yellow icon):** Represents ongoing work.
* **Published Versions (green checkmark):** Indicates live and accessible versions.
* **Older Versions (gray checkmark):** Indicates previously published versions.
