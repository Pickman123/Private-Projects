# Account-Level E2E Flow: Implementation Guide

This guide walks you through implementing account-level automations, including trigger setup, automation creation, testing, and publishing.

---

## 🌟 Overview

**Account-level automations** are used for sending notifications to users, regardless of individual site context. for more information about account level automations read the [Introduction](https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Introduction%20to%20Wix%20Official%20Notifications.md)

this docs include the steps you should do in order to create account level automation

1. Create an Automation Trigger
2. Test trigger
3. Create Preinstalled Automation
4. Test preinstalled Automation
5. Rollout

---

## 1️⃣ Create Automation Trigger

Account-level triggers can be implemented using one of the following methods:

- **Auto-Converted Trigger from Event:**  
  Use a server event (Legacy or DE) containing all relevant account/user data.
  
  <p align="left">
  <a href=./Triggers/Auto-Converted%20Triggers%20From%20Events%20(Account%20level).md
     style="display:inline-block;padding:8px 16px;background:#0063d1;color:#ffffff;font-weight:600;text-decoration:none;border-radius:4px;">
    ➡️ Auto-Converted&nbsp;Trigger&nbsp;From&nbsp;Event
  </a>
</p>  

- **Quix Job Trigger:**  
  Trigger automations for multiple users/accounts based on rows in a Quix job.
  
  <p align="left">
  <a href=./Triggers/Creating%20Trigger%20From%20Quix%20Job.md
     style="display:inline-block;padding:8px 16px;background:#0063d1;color:#ffffff;font-weight:600;text-decoration:none;border-radius:4px;">
    ➡️ Creating&nbsp;Trigger&nbsp;From&nbsp;Quix&nbsp;Job
  </a>
</p>  

---

## 2️⃣ Test trigger

- Thoroughly test account-level triggers to ensure your automation works end-to-end before release.
- Ensure the relevant feature toggle (`ft-...`, provided separately) is enabled for test environment.
   
<p align="left">
  <a href=https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/Triggers/Test%20Trigger.md
     style="display:inline-block;padding:8px 16px;background:#0063d1;color:#ffffff;font-weight:600;text-decoration:none;border-radius:4px;">
    ➡️ Test&nbsp;Trigger&nbsp;Guide
  </a>
</p>

---

## 3️⃣ Create Preinstalled Automation
Create the automation - define its logic, triggers, conditions, and notifications, and configure the accompanying pre-installed component.
Install the pre-installed component (with the app) only on production and test sites to ensure a controlled, correct rollout.

<p align="left">
  <a href="https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/Preinstalleds/PreInstalled%20Account%20Level%20Automation.md"
     style="display:inline-block;padding:8px 16px;background:#0063d1;color:#ffffff;font-weight:600;text-decoration:none;border-radius:4px;">
    ➡️ Create&nbsp;Pre-Installed&nbsp;Automation
  </a>
</p>

---

## 4️⃣ Test preinstalled Automation

- Thoroughly test the preinstalled component to ensure your automation works end-to-end before release.
- Ensure the relevant feature toggle (`ft-...`, provided separately) is enabled for test environment.

  <p align="left">
  <a href=https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/Triggers/Test%20Trigger.md
     style="display:inline-block;padding:8px 16px;background:#0063d1;color:#ffffff;font-weight:600;text-decoration:none;border-radius:4px;">
    ➡️ Test&nbsp;preinstalled&nbsp;Automation&nbsp;Guide
  </a>
</p>  

---

## 5️⃣ Rollout Time! 

🎉 Your account-level automation is ready for a gradual rollout and finalization. To do that:

- Include the production site (*msid:* `3dee5be0-fd3c-427a-8202-e74f27f7e8a5`) in your component spec
- Turned Off the Test env feature toggle (`ft-...`, provided separately)
- Publish your dev center app
- (identity team missing info about gradual rollout)

---

<p align="center">
  <b>✨ You did it! Time to automate and celebrate! ✨</b>
</p>
