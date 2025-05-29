# Welcome to Wix Official Notifications!

Welcome to the documentation for the **Wix Automations solution for notifications sent from Wix**. 

---

## ✨ What Are Wix Official Notifications?
Wix Official Notifications are automated emails or any other notifications sent directly from Wix to the users, ensuring every message is:

- **On-brand** 🟦
- **Consistent** 🔄
- **Automatic** 🤖

This guide is designed for Wix employees and provides a comprehensive overview of creating official notifications where Wix is both the sender and the brand.

> **Important:**  
> Before proceeding, confirm that both the sender and brand should be Wix.  
> If unsure, consult the Marketing team.

---

## Account-Level vs. Site-Level Automations

Understanding whether an automation operates at the **account level** or **site level** is essential, as it affects implementation, design, and data flow.

---

### Site-Level Automations

Site-level automations are triggered by events specific to individual sites.

**Examples:**
- 🛒 An order is placed on a site → Order confirmation email is sent.
- 👯 A new collaborator is added to a site → Invitation email is sent.

---

### Account-Level Automations

Account-level automations are associated with the unified Wix account, which can span multiple workspaces or sites. Users within an account can collaborate across workspaces, and certain actions or settings apply universally at the account level.

**Examples:**
- 🔑 A user clicks “Reset Password” → Password reset email is sent.
- 💳 A payment method is updated for a workspace → Billing notification is sent to the account owner.

---

## Automation Logic & Key Differences

This section explains how automations are implemented under the hood and highlights the core differences between site-level and account-level automation logic.

### Site-Level Automation Logic

- Automations are defined in a pre-installed automation component under a Dev Center app.  
- This component is automatically installed on every site where the app is present.  
- Site-level automations and the notifications they generate are triggered by site-specific events and are sent to the site owner or other collaborators.  
- These automations run invisibly in the background and are not exposed or editable by users.
- Audience is determined by the trigger payload (email fields or contact ID) or by site collaborators (e.g., the site owner).
### Account-Level Automation Logic

- Account-level automations are defined in a pre-installed automation component under a Dev Center app.  
- This app, along with its automation component, is installed only on a single production site and a dedicated test site.  
- The production site is responsible for triggering all account-level automations and sending the corresponding notifications to users.
- Audience can be based on the trigger payload—formatted email fields or the userID included in the event aspect.

#### 🥊 Key Differences

| Feature                | **Site-Level Automations**                                                  | **Account-Level Automations**                                                  |
|------------------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Triggers**           | Site-specific events (e.g., form submitted, order placed)                   | Account-wide events (e.g., password updates, subscription changes)                |
| **Audience**           | Site collaborators or based on trigger payload (email/contact ID)           | Based on trigger payload or event aspect (email fields or user ID in the event)        |
| **Installation**       | Automatically added to each site with the app                               | The App should be Manually installed only on production + test site only         |
| **Execution Context**  | Executes inside each site separately                                        | Executes from the central production site only                                 |
| **User Visibility**    | Not visible or editable by site users                                       | Not visible or editable by users                                                   |
---

<div align="right">

➡️ [Continue to: Prerequisites for Sending Wix Official Notifications → ](./Prerequisites%20for%20Sending%20Wix%20Official%20Notifications.md)

</div>
