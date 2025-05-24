# Official Wix Emails – Action Configuration Guide

## Introduction

This guide explains how to configure and customize email notifications using the "Send an Email" action, sent from Wix as the sender and brand (official emails), as part of the preinsatlled automation component creation.

---

## Context

Official Wix emails require specific configuration to ensure accurate targeting and reliable delivery.  
This process applies equally to both site-level and account-level automations.

---

## Step-by-Step Configuration

### 1. Start with Preinstalled Automation Component Guide - [link here](https://github.com/Pickman123/Private-Projects/blob/main/documentations/Account-Level%20Preinstalled%20Automation%20Component%20implementations%20guide.md#preinstalled-automation-component-implemetations-guide-account-level)

Before configuring emails, you should start creating an automation ensure you have followed the guide for creating preinstalled automation components.

---

### 2. Select the “Send an Email” Action

In your automation flow, add the **Send an Email** action.

_Image: Add "Send an Email" action_

---

### 3. Ensure the Widget Is Set to Wix official emails State

Verify that the "Send an Email" action widget is in Wix official emails State. The interface will look different than the standard interface.

_Image: Wix official emails State action interface_

> **Important:** If the interface does not match the example, re-enter the automation builder before proceeding.

---

### 4. Define the User Type

Choose the audience for this email—**Wix Studio** or **Classic** users.  
This must match your condition logic in the automation.

- Select the user type in the action’s settings.
- **Note:** Changing the audience from Classic to Studio (or vice versa) resets the action to its default state (template, recipients, etc).

_Image: Setting panel for user type_

---

### 5. Sender Details

Sender details are read-only and automatically set based on the audience chosen.  
No changes are required here.

---

### 6. Select and Design the Email Template

- Click **Choose Template** and pick the relevant template for Studio or Classic.
- Templates have pre-defined themes; any new elements you add will be styled accordingly.

‼️ **Must read:**  
Refer to the [Email Design Guidelines on Figma](#) for best practices and requirements.

_Image: Entry point to email template selection_

---

### 7. Email Template Creation

- Edit your email content and layout as needed.
- **No need to include unsubscribe links:** Official Wix emails should be transactional and do not require unsubscribe options.
- **Logo and footer are locked:** These regions follow Wix branding and cannot be edited.

_Image: Email template editing UI_

---

### 8. Use Dynamic Variables

You can insert dynamic placeholders in your email, using fields available in your trigger schema.  
These work in both text and links.

**Supported out-of-the-box dynamic placeholders (case-sensitive):**
- `${metaSite.Id}`
- `${website.Name}`

_Image: Dynamic variables in use_

---

### 9. Template Translations & Localization

#### 9.1 Initiate Localization

- By default, you edit the English version.  
- Once finalized, the UX writer should click **Save and create keys** to start localization.

> Only click this when the English content and layout are complete.

_Image: Entry point for localization_

#### 9.2 Create File Name

- Enter a descriptive file name for Smartling (e.g. `booking-confirmation-letter`).  
- Use hyphens to separate words.

_Image: File name input UI_

#### 9.3 Create Key Names

- Name each key descriptively (e.g. `email.confirmation.code`), using dots to separate words.
- Keys should be unique within the email.
- Consult your localization manager if unsure.
- Click **Confirm & Sync** once done.

_Image: Key creation UI_

#### 9.4 Success Modal

- A modal displays the file and key names.
- Share the file name with your localization manager to start the process in Smartling.
- Click **Show Keys** in the “Send an Email” action at any time to review.

_Image: Success modal_

> **VERY IMPORTANT:**  
> Once an email is synced with Smartling, **do not duplicate** the automation! Duplicating will affect the original Smartling file.

#### 9.5 Editing a Localized Email

- Editing after keys are created may require creating new keys or updating existing ones.
- Always repeat the localization process for updated or new keys.

_Image: Editing localized email_

#### 9.6 Previewing and QA’ing Translations

- Use **Preview & Test** to view and send test emails in different languages.
- Preview translations published in Smartling to verify correctness.

_Image: Preview and test entry points_

#### 9.7 Publishing Translations to Production

> **Very Important:**  
> Translations are published to production when you upload the generated automation link to Dev Center.  
> All languages are published as-is—make sure all translations are ready.  
> Partial translations in progress will be reflected live if you publish early.  
> Changing or adding keys in a localized automation and re-uploading the link before localization is complete will cause those parts to appear in English in production.

---

### 10. Set Recipients

- This setting is saved in the pre-installed configuration and determines the default recipient.
- Choose “Emails from trigger” for recipient options:
  1. If sending the user ID as the recipient, select "primary email."
  2. Any email-format field in the trigger schema can also be selected.

_Image: Set recipients panel_

---

### 11. Repeat for Classic or Studio (as needed)

- Complete the setup for both Classic and Studio if your automation supports both audiences.

_Image: Step completion for Studio/Classic_

---

## Next Steps

Continue to the [Preinstalled Automation Component creation guide](https://github.com/Pickman123/Private-Projects/blob/main/documentations/Account-Level%20Preinstalled%20Automation%20Component%20implementations%20guide.md#preinstalled-automation-component-implemetations-guide-account-level) to complete setup.

---
