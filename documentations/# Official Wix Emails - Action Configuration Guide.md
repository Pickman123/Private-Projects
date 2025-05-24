# Official Wix Emails - Action Configuration Guide

## Introduction

This guide explains how to configure and customize email notifications using the "Send an Email" action that being sent from wix as sender and brand. (official emails) 
 
It will help you ensure your account-level automations send the correct emails to the right users, with the proper content and design.

## Context

Emails that are being sent from Wix as sender and brand requieinring adjsutments, you must use the correct interface and settings to guarantee accurate targeting and deliverability.  
This guide will walk you through each step, highlight important notes, and point to official design resources.

This part act the same for site level and account level official wix emails

---

*before start, make sure to start with the guide of creating preinsatelld automation component guide - link*

### 6.1 Select the “Send an Email” Action

In your automation flow, add the "Send an Email" action.

_image_

---

### 6.2 Ensure the Widget Is Set to the Wix official emails State

When creating a Wix Automation, the "Send an Email" action widget should reflect the Wix official interface, which looks different from the standard interface:

_image of the  Wix official interface 

> **Important:**  
> If you do not see the interface as shown above, try re-entering the automation builder as before.

---

### 6.3 Define the User Type

Define which audience will receive the email—Wix Studio or Classic users.  
This must align with your condition logic above the action. (see more details on that here creating preinsatelld automation component guide - link )

- Select the appropriate user type in the action’s settings.
- **Note:** Changing the audience from Classic to Studio (or vice versa) will reset the action to its default state (template and recipients will be reset).

_image of the setting panel_

---

### 6.4 Sender Details

The sender details field is read-only. Sender information is automatically determined based on the audience you selected.

---

### 6.5 Select and Design the Email Template

- Click **Choose Template** to pick the relevant template for your audience (Studio or Classic).
- Templates have pre-defined themes; any new elements you add will be styled accordingly.

‼️ **Must read:**  
Refer to the [Email Design Guidelines on Figma](#) for best practices and requirements.

_image of entry point to email template_

---

<!-- Continue from here when ready: add sections for editing content, previewing emails, translations, testing, and troubleshooting as needed. -->
