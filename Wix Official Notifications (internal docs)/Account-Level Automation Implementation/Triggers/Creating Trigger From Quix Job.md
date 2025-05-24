# Creating Trigger from Quix Job

Automations can be initiated directly from Quix jobs. These triggers can operate at either the *site level* or *account level*, depending on your use case.

---

## Overview

A trigger from a Quix job allows you to run an automation action for every row in your Quix job's output.

- **Site-level triggers:** Target specific sites based on data in each row.
- **Account-level triggers:** Target users, sending notifications across workspaces or to specific recipients.

The implementation includes steps on both the **Dev Center** and **Quix** platforms.

---

## Dev Center Setup

### 1. Define a Trigger Component

In Dev Center, create a trigger component *from scratch* for your app.

- The trigger schema should mirror the Quix job's columns.
- Each schema field should use the same terminology as the Quix column name, and the data type/format must match the value sent at runtime.

**Useful Links:**
- [Trigger Payload Schema Documentation](https://dev.wix.com/docs/rest/business-management/automations/triggers/the-trigger-payload-schema)
- [How to Set Up a Trigger Component in Dev Center](https://dev.wix.com/docs/rest/business-management/automations/triggers/add-a-trigger-to-your-app)

---

## Quix Side Setup

### 1. Job Definition

Design your Quix job to include all the data needed for your automation and notifications.

#### Mandatory Fields (Differs by Trigger Level):

- **Site-Level:**  
  - The job *must* include an `msid` column.
  - Behind the scenes, this is pushed into the event aspect so the automation runs on the correct site as specified by `msid`.

- **Account-Level:**  
  - The job should include a `userId` or `email` column to identify the recipients.

### 2. Connect the Job to Your Trigger

In the Quix Job UI, select:  
  - **Action → Automations → Site-level** *or* **Account-level**
  - For account-level jobs, specify if the trigger is for testing or production.
- Enter the relevant *appId* and *trigger key* (from Dev Center).

![Quix Job UI Example](https://github.com/Pickman123/Private-Projects/blob/main/docs%20images/Quix%20image.png?raw=true)

---

## 3. Execution

- Run the job.
- The automation will be triggered for *each row* in the job.

---

## Important Notes

- **Automations are triggered row by row**—each output row results in a separate automation.
- **Target population is your responsibility:**  
  There is **no validation** by Automations or Wix Email systems to ensure a user or site did not already receive a message.
- **Deduplication:**  
  If you require deduplication, you must manage it in your Quix job or data source.

---

<div align="right">

➡️ [Continue to: Test Your Trigger →](./TEST_YOUR_TRIGGER.md)

</div>
