# Prerequisites for Sending Wix Official Notifications
*(For both Site-Level and Account-Level Automations)*

---

## 1. Ideation & Research  
**Owners:** PM & Developer

- Review the basics of Wix Automations: [Automation Introduction](https://dev.wix.com/docs/rest/business-management/automations/introduction)
- Understand automation triggers: [Triggers Overview](https://dev.wix.com/docs/rest/business-management/automations/triggers/about-triggers)
- Learn about pre-installed automation components: [About Pre-Installed Automations](https://dev.wix.com/docs/rest/business-management/automations/automations/pre-installed-automations/about-pre-installed-automations)
- Define which notifications are required and classify them as account-level or site-level.
- Identify the key data needed for each notification.

---

## 2. Application Setup  
**Owner:** Developer

1. Get familiar with the Dev Center environment and app management: [Dev Center Guide](https://dev.wix.com/docs/build-apps/get-started/templates/build-an-app-template-guide-for-wix-employees)
2. Check if an approved or published application already exists for your use case.  
   *Note: Site-level and account-level notifications must be implemented in separate apps.*
3. If creating a new app for site-level notifications, decide if it should be:
    - **Core app:** Installed by default on all user sites (requires coordination with the Automation Platform team).
    - **On-demand app:** Installed by users or triggered by specific actions.

---

## 3. Event Identification  
**Owner:** Developer

- Determine if an existing event provides all the data required to trigger the automation.
- If such an event exists, leverage it to streamline the implementation.

---

# Implementation  
*(Follow the guide appropriate for your automation level)*

- **[Account-Level Implementation Guide →](./Account-Level%20Automation%20Implementation/E2E%20Flow.md)**
- **[Site-Level Implementation Guide →](./Account-Level%20Automation%20Implementation/E2E%20Flow.md)**

Each guide covers:
- Trigger implementation options (auto-converter, RPC, Quix job)
- Automation creation and email design
- Testing flow (including test site setup)
- Publishing process

---
