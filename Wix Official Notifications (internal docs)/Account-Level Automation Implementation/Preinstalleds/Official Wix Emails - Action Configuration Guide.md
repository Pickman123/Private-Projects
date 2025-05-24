# Official Wix Emails – Action Configuration Guide

## Introduction

This guide explains how to configure and customize email notifications using the "Send an Email" action, sent from Wix as the sender and brand (official emails), as part of the preinstalled automation component creation.

---

## Context

Official Wix emails require specific configuration to ensure accurate targeting and reliable delivery.  
This process applies equally to both site-level and account-level automations.

---

## Step-by-Step Configuration

### 1. Start with Preinstalled Automation Component Guide - [link here](./PreInstalled%20Automation.md)

### 2. Select the “Send an Email” Action

### 3. Ensure the Widget Is Set to Wix official emails State

### 4. Define the User Type

### 5. Sender Details

### 6. Select and Design the Email Template

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

This setting is saved in the pre-installed configuration and determines the default recipient.

- Choose “Emails from trigger” for recipient options:
  1. If sending the user ID as the recipient, select "primary email."
  2. Any email-format field in the trigger schema can also be selected.

_Image: Set recipients panel_

---

### 11. Repeat for Classic or Studio (as needed)

Complete the setup for both Classic and Studio if your automation supports both audiences.

_Image: Step completion for Studio/Classic_

---

## Next Steps

Continue to the [Preinstalled Automation Component creation guide](./PreInstalled%20Automation.md) to complete setup.

---
