# Account-Level E2E Flow: Implementation Guide

This guide walks you through implementing account-level automations, including trigger setup, automation creation, testing, and publishing.

---

## 1. Overview

**Account-level automations** are used for sending notifications to users or accounts, regardless of individual site context. for more information read the [Introduction](https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Introduction%20to%20Wix%20Official%20Notifications.md)

---

## 2. Trigger Implementation Options

Account-level triggers can be implemented using one of the following methods:

- **Auto-Converted Trigger from Event:**  
  Use a server event (Legacy or DE) containing all relevant account/user data.  
  See: [Auto-Converted Triggers From Events](./Triggers/Auto-Converted%20Triggers%20From%20Events%20(Account%20level).md)

- **Quix Job Trigger:**  
  Trigger automations for multiple users/accounts based on rows in a Quix job.  
  See: [Creating Trigger From Quix Job](./Triggers/Creating%20Trigger%20From%20Quix%20Job.md)

---

## 3. Trigger Testing Flow

- Thoroughly test account-level triggers to ensure your automation works end-to-end before release.
- Ensure the relevant feature toggle (`ft-...`, provided separately) is enabled for test environment.  

### 3.1 Install Your App on the Test Site

- Use the **"Test Your App"** feature in Dev Center to install your app on the dedicated test site:  
  *msid:* `eb2f2d49-b70f-4b9d-9055-4cc9793aca5e`
  
  ![Install App for test](../../images/Install%20app%20for%20test.png?raw=true)

  *Notes:*
  - If you are not a collaborator, contact [#Automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).
  - If the app is already installed, you do not need to install it again.

### 3.2 Create an Automation with Your Trigger

- On the test site, create a new automation with your account-level trigger—any automation you prefer—and verify that it runs successfully.

### 3.3 Manually Run the Trigger

- **For Auto-Converted Triggers:**  
  Initiate the trigger manually and verify that it runs successfully. 
- **For Quix-Based Triggers:**  
 In the Quix Job settings, choose the Testing configuration for your automation action, then initiate it from there.

### 3.4 When satisfied, publish the trigger.

  ![Publish Trigger Example](../../images/Publish%20account%20level%20emails.png?raw=true)

---

## 4. Create Preinstalled Automation Component
Create the automation—define its logic, triggers, conditions, and email notifications—and configure the accompanying pre-installed component.
  
  *Notes:*
- Install the pre-installed component (with the app) only on production and test sites to ensure a controlled, correct rollout.

**Implementation Details**
For complete instructions, see the full guide: [Account-Level Pre-Installed Automation Implementation Details](https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/Preinstalleds/PreInstalled%20Automation.md)


## 4. Test preinstalled in the dedicated site

Thoroughly test the preinstalled component to ensure your automation works end-to-end before release.

Ensure the relevant feature toggle (`ft-...`, provided separately) is enabled for test environment.   

### 6.1: Install Your App on the Test Site

- Use the **"Test Your App"** feature in Dev Center to install your app on the dedicated test site:  
  *msid:* `eb2f2d49-b70f-4b9d-9055-4cc9793aca5e`
  
  ![Install App for test](../../images/Install%20app%20for%20test.png?raw=true)


  *Notes:*
  - If you are not a collaborator, contact [#Automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).
  - If the app is already installed, you do not need to install it again.

### 6.2: Find your preinstalled in the automations page

Find your preinstalled automation under "installed for you" tab in the table

### 6.2: Run the automation 


