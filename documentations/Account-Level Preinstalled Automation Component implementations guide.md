# Preinstalled Automation Component implemetations guide (Account level) 
# Account-Level Preinstalled Automation Component implemetations guide 

## Introduction

This step covers the creation of the automation itself, including its logic, trigger, conditions, and email notifications, as well as the setup of the pre-installed component.

For account-level automations, the pre-installed component (along with the app) must be installed only on the production and test sites. This ensures correct deployment and controlled rollout.

---

## 1. Create the Base Automation

**What is base automation?**  
This is the core automation configuration that defines the logic, structure, and messaging of the automation.  
**Important note:** This automation should be reused every time the pre-installed automation is updated.

### Steps

1. Go to your Dev Center app and navigate to the automations page.

   *Note: If you don't yet have a dedicated app for account-level automations, make sure to follow our prerequisites guide ([link]).*

   _image: automations Dev Center page_

2. Click on **Create New Preinstalled Components**, and select your dedicated site where you manage your base automations in order to create a new one.
   
   *Note: Look for your team site here: [Team Sites List](https://docs.google.com/spreadsheets/d/1nlqcgy7C_8N5t0FsUWgLDB3nfQhNZbV-YSw4IZ9zr7U/edit?gid=0#gid=0).  
   If you don't have one, reach out in #automation platform.*

   _image: create new preinstalled_  
   _image: select new site in the preinstalled_

3. Go to the automation page → make sure the following Feature toggle (provided later) is ON and that your site is with Advanced Mode ON → Create new account-level automation.

   _image: Advanced Mode ON_  
   _image: the dropdown_

4. Select your account-level trigger from the trigger catalog.

   _image: selecting trigger from Figma_

5. Set the automation logic.

   A common use is to set a condition to route the visitor based on their site type (e.g. Studio vs. Classic Editor). The needed data will be available out of the box.

   _image: the condition_

   Any other functionality or logic can be implemented in this part according to your needs.

6. Set the automation notification.

   - [Emails setup guide →](#)  
   - [Push notifications guide →](#)

7. Activate the automation in the builder.

---
## 2. Improt base automation configuration into the preinstalled components



## 2. Set Up the Rollout Spec

Generate a spec (feature toggle) with your scope in Guinipig.  
This will control rollout and prevent the component from being downloaded on the production site if the app is already installed.

---

## 3. Export the Automation Link

- Generate a link from the automation table.
- The link includes a reference to the automation configuration and will be used to create or update the pre-installed component.

---

## 4. Complete the Pre-Installed Setup in Dev Center

- Go to the Dev Center → Pre-installed form.
- Paste the exported link.
- Name the pre-installed automation clearly.
- Save it under the relevant spec.

---
