# Create Preinstalled Automation Component (account level)

## 🌟 Overview

This guide covers the creation of the automation itself—including logic, triggers, conditions, and email notifications—as well as the setup of the pre-installed component.

For account-level automations, the pre-installed component (along with the app) must be installed only on the production and test sites. This ensures correct deployment and controlled rollout.

---

## 1️⃣ Create the Base Automation

**What is base automation?**  
This is the core automation configuration that defines the logic, structure, and messaging of the automation.  
**Important note:** This automation should be reused every time the pre-installed automation is updated.

### Steps

1. Go to your Dev Center app and navigate to the automations page.

   *Note: If you don't yet have a dedicated app for account-level automations, make sure to follow our [prerequisites guide](https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Prerequisites%20for%20Sending%20Wix%20Official%20Notifications.md).*

   _image: automations Dev Center page_

2. Click on Create New Preinstalled Components, and select your dedicated site where you manage your base automations in order to create a new one.
   
   *Note: Look for your team site here: [Team Sites List](https://docs.google.com/spreadsheets/d/1nlqcgy7C_8N5t0FsUWgLDB3nfQhNZbV-YSw4IZ9zr7U/edit?gid=0#gid=0).  
   If you don't have one, reach out in #automation platform.*

   _image: create new preinstalled_  
   _image: select new site in the preinstalled_

3. Go to the automation page → make sure the relevant Feature toggle (provided later) is ON and that your site is with Advanced Mode ON → Create new account-level automation.

   _image: Advanced Mode ON_  
   _image: the dropdown_

4. Select your account-level trigger from the trigger catalog.

   _image: selecting trigger from Figma_

5. Implement the user-type conditional template routing (Required for Email Sending)

   Add to the automation a single condition that will route the user to the right email design according to user-type (Studio or Classic account). User-type data is available by default, so no additional setup is required.

   _image: the condition_

   Any other functionality or logic can be implemented in this part according to your needs.

### 1.2 Set the automation notification.

  <p align="left">
  <a href=https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/Preinstalleds/Official%20Wix%20Emails%20-%20Action%20Configuration%20Guide.md
     style="display:inline-block;padding:8px 16px;background:#0063d1;color:#ffffff;font-weight:600;text-decoration:none;border-radius:4px;">
    ➡️ Emails&nbsp;setup&nbsp;guide
  </a>
</p>

--- 

 <p align="left">
  <a href=#
     style="display:inline-block;padding:8px 16px;background:#0063d1;color:#ffffff;font-weight:600;text-decoration:none;border-radius:4px;">
    ➡️ Push&nbsp;notifications&nbsp;guide
  </a>
</p>  

--- 

### 1.3 Activate the automation in the builder.

   _image: activation_

---

## 2️⃣ Set Up the Rollout Spec

- Generate a spec (feature toggle) with your scope in [Guinipig →](https://wix-bo.com/dev/feature-toggle?viewId=views).
- Set it to true for the dedicated test site (**msid:** `eb2f2d49-b70f-4b9d-9055-4cc9793aca5e`)  
  This will control rollout and prevent the component from being downloaded on the production site if the app is already installed.

---

## 3️⃣ Export the Base Automation into the Preinstalled Automation Component

- Generate a link from the automation table.
- The link includes a reference to the automation configuration and will be used to create or update the pre-installed component.

  _image: export link_

---

## 4️⃣ Complete the Pre-Installed Setup in Dev Center

- Go to the Dev Center → Automations page → create new pre-installed.
- Paste the exported link.
- Name the pre-installed automation clearly.

  _image: create new preinstalled_
  _images of preinstalled form_

---

## 5️⃣ Save the Preinstalled Under Spec

  _image of spec modal_

---
<div align="right">

➡️ [Continue to: testing your preinstalled component → ](https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/E2E%20Flow.md)

</div>

