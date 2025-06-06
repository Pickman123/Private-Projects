# Test Your Account Level Trigger
- Thoroughly test account-level triggers to ensure your automation works end-to-end before release.
- Ensure the relevant feature toggle (`specs.automations.AccountLevelAutomationsTestMode`) is enabled for test environment.

---

## 1️⃣ Install Your App on the Test Site

- Use the **"Test Your App"** feature in Dev Center to install your app on the dedicated test site:  
  *msid:* `eb2f2d49-b70f-4b9d-9055-4cc9793aca5e`
  
  ![Install App for test](https://github.com/Pickman123/Private-Projects/blob/main/docs%20images/Install%20app%20for%20test.png?raw=true)

  *Notes:*
  - If you are not a collaborator, contact [#Automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).
  - If the app is already installed, you do not need to install it again.

---

## 2️⃣ Create an Automation with Your Trigger

- On the test site, create a new automation with your account-level trigger—any automation you prefer—and verify that it runs successfully.

---

## 3️⃣ Run the Trigger with spec ON (`specs.automations.AccountLevelAutomationsTestMode`)

**Manually**
- *For Auto-Converted Triggers:*  
  Initiate the trigger manually and verify that it runs successfully. 
- *For Quix-Based Triggers:*  
 In the Quix Job settings, choose the Testing configuration for your automation action, then initiate it from there.

**Fire console**
- Make sure to add the expirement before firing

---

## 4️⃣ When satisfied, publish the trigger

  ![Publish Trigger Example](https://github.com/Pickman123/Private-Projects/blob/main/docs%20images/Publish%20account%20level%20emails.png?raw=true)

---

<div align="right">

➡️ [Continue to: Creating preinstalled automation → ](https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/Preinstalleds/PreInstalled%20Automation.md)

</div>
