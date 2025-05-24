# Auto-Converted Trigger From Event (Account level)

Auto-converted triggers provide a streamlined and efficient way to create and manage automation triggers in Wix, leveraging existing events defined in your app.

---

## Related Documentation

- [About automations](https://dev.wix.com/docs/rest/business-management/automations/introduction)
- [About triggers](https://dev.wix.com/docs/rest/business-management/automations/triggers/about-triggers)
- [Trigger payload schema](https://dev.wix.com/docs/rest/business-management/automations/triggers/the-trigger-payload-schema)

---

## Introduction

A **trigger** is the entry point for automation—an event that activates an automated process.  
With Wix, any event (DE or legacy) can automatically be converted into an automation trigger, allowing you to leverage existing or new events with minimal effort.

> **Note:**  
> By default, a newly converted trigger is created as a "not publish" draft. See the steps below to publish your trigger.

---

## How Events Become Triggers & Stay Synced

A dedicated service monitors qualifying events. When an event is created or updated:
- The service extracts the proto schema (public fields only).
- A matching trigger schema is generated.
- The trigger remains unpublished until you release it.

**Key Points:**
- One trigger is generated per event.
- Proto changes are automatically reflected in the trigger.
- Maintenance is handled through the event’s proto definition.

---

## Initial Requirements

Before starting, ensure you have the following:

1. **App ID:**  
   The event entity must include an [appDefId](https://github.com/wix-private/server-infra/blob/master/framework/protos/src/main/proto/wix/api/entity.proto#L59).

2. **Exposure:**  
   - `"PUBLIC"`: Use `wix.api.event`, `wix.api.domain_event`, or `wix.api.callback` (callback is deprecated).
   - `"PRIVATE"`/`"INTERNAL"`: Conversion is possible via whitelist—contact [#automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).

3. **Valid Segment:**  
   The event/entity must use the **Users** or **Public** segment ([entity](https://github.com/wix-private/server-infra/blob/master/framework/protos/src/main/proto/wix/api/entity.proto#L53), [event](https://github.com/wix-private/server-infra/blob/master/framework/protos/src/main/proto/wix/api/callback.proto#L90)).

4. **Partitioning:**  
   High-traffic topics must be defined in Greyhound with multiple partitions (ideally 10+). For help, contact [#automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).

5. **Legacy Event Slug:**  
   For legacy events, add a `slug` to the event schema or use headers:
   - Add as a `slug` property or via [this aspect](https://github.com/wix-private/wix-automations/blob/master/domain-events-reporter/event-reporter-worker/src/main/scala/com/wixpress/automations/reporter/v1/AutomationsEventReportingContext.scala#L5).
   - In your `BUILD.bazel`:
     ```
     deps = [ ...,
     "@wix_automations//domain-events-reporter/event-reporter-worker/src/main/scala/com/wixpress/automations/reporter/v1:server",
     ```
   - Example usage:
     ```scala
     import com.wixpress.automations.reporter.v1.AutomationsEventReportingContext

     // Pass this callscope when producing the message to kafka
     val csWithAspect = callScope.withAspect[AutomationsEventReportingContext](AutomationsEventReportingContext(slug = Some(???)))
     ```

---

After meeting these requirements, send the following information to [#automations-platform](https://wix.slack.com/archives/C7F2DUC1Y):

- AppId
- Topic
- Slug
- Exposure (add PRIVATE/INTERNAL events to whitelist)

Your event will appear in Dev Center as a "not publish" trigger, ready for configuration and release.

![Table](https://mcusercontent.com/2b2caa8a533bc21aa54a3ba9b/images/b72cb154-638e-9c64-f6b4-de54c18fbce7.png "Table")

---

## Finalizing Trigger Creation

1. **Locate the Trigger:**  
   In Dev Center, find the desired event trigger by topic and slug.

2. **Mark as Account-Level Trigger:**  
   Edit the trigger and mark it as "account-level eligible" if it should be used for account-level automations.

   ![Edit Trigger](https://github.com/Pickman123/Private-Projects/blob/main/docs%20images/Edit%20Trigger.png?raw=true)
   ![Account level trigger](https://github.com/Pickman123/Private-Projects/blob/main/docs%20images/Select%20account%20level%20trigger.png?raw=true)

3. **Mark User ID in Aspect (if needed):**  
   If the notification audience is based on the userID from the aspect, ensure it is marked for correct usage at runtime.

4. **Enrich Trigger Functionality (if needed):**
   - Update the [trigger payload schema](https://dev.wix.com/docs/rest/business-management/automations/triggers/the-trigger-payload-schema) (add required fields, special annotations, etc.).
   - Enable scheduling ([how-to](https://dev.wix.com/docs/rest/business-management/automations/triggered-events/internal-creating-a-new-automations-trigger)).
   - Add SPI endpoints ([about SPI endpoints](https://dev.wix.com/docs/build-apps/develop-your-app/extensions/backend-extensions/service-plugins/about-service-plugin-extensions)).
   - Add [filters](https://dev.wix.com/docs/rest/business-management/automations/triggers/filter-fields) to payload fields if needed.

---

## Editing Trigger Schema: What Goes Where

Auto-converted triggers are based on your proto file, but some aspects can be managed directly in Dev Center.

**overview**:
*The trigger schema’s structure and field order are fixed by your proto definition: in the Dev Center you can’t add, remove, or rename fields—you can only annotate them.* 

### Proto-Based Annotations

| Annotation Name | Description                         |
|-----------------|-------------------------------------|
| Type            | Data type of the field              |
| Format          | Available formats for string fields |
| oneOf (enum)    | Field with predefined values        |

### Editable in Dev Center

| Annotation Name      | Description                                                           |
|---------------------|-----------------------------------------------------------------------|
| title               | User-friendly field name (for Automations Builder)                    |
| examples            | Example values for setup                                              |
| description         | Brief explanation of field purpose                                    |
| required            | Marks the field as mandatory                                          |
| futureDate          | Allows future date/time for scheduled triggers                        |
| Items Selection SPI | Enables user selection of items via SPI (any ID field should support) |
| ORDER_ID            | Links trigger to actions that require an order ID                     |
| IMAGE_URL           | Displays a dynamic image from a URL (e.g., in email content)          |
| ATTACHMENT          | Allows adding attachments via URL and filename (for email)            |
| hidden              | Hides the field from users                                            |
| MONEY               | Represents a monetary value (currency + amount)                       |

---

**After completing these steps, your trigger will be in draft mode and ready for testing.**

![Draft trigger ready](https://github.com/Pickman123/Private-Projects/blob/main/docs%20images/Draft%20Trigger%20created%20and%20ready%20for%20testing.png?raw=true)

---

<div align="right">

➡️ [Continue to: Test Your Trigger →](https://github.com/Pickman123/Private-Projects/blob/main/Wix%20Official%20Notifications%20(internal%20docs)/Account-Level%20Automation%20Implementation/Triggers/Test%20Trigger.md#test-your-account-level-trigger)

</div>
