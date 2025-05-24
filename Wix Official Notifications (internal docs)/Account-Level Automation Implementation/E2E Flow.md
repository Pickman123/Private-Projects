# Account-Level E2E Flow: Implementation Guide

This guide walks you through implementing account-level automations, including trigger setup, automation creation, testing, and publishing.

---

## 1. Overview

**Account-level automations** are used for sending notifications to users or accounts, regardless of individual site context.

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

### Step 3.1: Install Your App on the Test Site

- Use the **"Test Your App"** feature in Dev Center to install your app on the dedicated test site:  
  *msid:* `eb2f2d49-b70f-4b9d-9055-4cc9793aca5e`
  
  ![Install App for test](../../images/Install%20app%20for%20test.png?raw=true)

  *Notes:*
  - If you are not a collaborator, contact [#Automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).
  - If the app is already installed, you do not need to install it again.

### Step 3.2: Create an Automation with Your Trigger

- On the test site, create a new automation using your account-level trigger and configure the desired actions (e.g., notifications, emails).

### Step 3.3: Manually Run the Trigger

- **For Auto-Converted Triggers:**  
  Ensure the relevant feature toggle (`ft-...`, provided separately) is enabled for test environment.  
- **For Quix-Based Triggers:**  
  In the Quix Job configuration, select the "testing" configuration for your automation action.

---

### Step 3.4: Review and Debug Automation Results

- Monitor the automation execution results on the test site.
- Check that notifications are sent to the correct addresses and that the payload data is accurate.
- If the automation fails or produces unexpected results, revisit your trigger schema, make sure the FT is indeed ON, or Quix job setup and test again.

  ![Publish Trigger Example](../../images/Publish%20account%20level%20emails.png?raw=true)

---

## 4. Create Preinstalled Automation Component

This step covers the creation of the automation itself, including its logic, triggers, conditions, and email notifications, as well as the setup of the pre-installed component.

For account-level automations, the pre-installed component (along with the app) must be installed only on the production and test sites. This ensures correct deployment and controlled rollout.

For full implementation details, see:  
[Account-Level Preinstalled Automation Implementation Details](./Preinstalleds/PreInstalled%20Automation.md)



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


