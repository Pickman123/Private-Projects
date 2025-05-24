# Auto-Converted Triggers From Events (Account level)

Auto-converted triggers provide a streamlined and efficient way to create and manage automation triggers in Wix, leveraging existing events defined in your app.

---

## Related Documentation

- [About automations](https://dev.wix.com/docs/rest/business-management/automations/introduction)
- [About triggers](https://dev.wix.com/docs/rest/business-management/automations/triggers/about-triggers)
- [Trigger payload schema](https://dev.wix.com/docs/rest/business-management/automations/triggers/the-trigger-payload-schema)

---

## Initial Requirements

Before starting, ensure you have the following:

1. **App ID:**  
   The event entity must include an `appDefId`.

2. **Exposure:**  
   - `"PUBLIC"`: Use `wix.api.event`, `wix.api.domain_event`, or `wix.api.callback` (callback is deprecated).
   - `"PRIVATE"`/`"INTERNAL"`: Conversion is possible via whitelist—contact [#automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).
3. **Valid Segment:**  
   The event/entity must use the **Users** or **Public** segment ([entity](https://github.com/wix-private/server-infra/blob/master/framework/protos/src/main/proto/wix/api/entity.proto#L59), [event](https://github.com/wix-private/server-infra/blob/master/framework/protos/src/main/proto/wix/api/entity.proto#L53)).

4. **Partitioning:**  
   High-traffic topics must be defined in Greyhound with multiple partitions (ideally 10+). For help, contact [#automations-platform](https://wix.slack.com/archives/C7F2DUC1Y).

5. **Legacy Event Slug:**  
   For legacy events, add a `slug` to the event schema or use headers:
   - Add as a `slug` property or via [this aspect](https://github.com/wix-private/wix-automations/blob/master/domain-events-reporter/event-reporter-worker/src/main/scala/com/wixpress/automations/reporter/v1/AutomationsEventReportingContext.scala#L5).
   - In your `BUILD.bazel`:
     ```
     deps = [ ...,
       "@wix_automations//domain-events-reporter/event-reporter-worker/src/main/scala/com/wixpress/automations/reporter/v1:AutomationsEventReportingContext.scala#L5",
     ]
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

![Table](../../../images/Table.png?raw=true)

---

## Finalizing Trigger Creation

1. **Locate the Trigger:**  
   In Dev Center, find the desired event trigger by topic and slug.

2. **Mark as Account-Level Trigger:**  
   Edit the trigger and mark it as "account-level eligible" if it should be used for account-level automations.

   ![Edit Trigger](../../../images/Edit%20Trigger.png?raw=true)
   ![Account level trigger](../../../images/Select%20account%20level%20trigger.png?raw=true)

3. **Mark User ID in Aspect (if needed):**  
   If the notification audience is based on the userID from the aspect, ensure it is marked for correct usage at runtime.

4. **Enrich Trigger Functionality (if needed):**  
   - Update the [trigger payload schema](https://dev.wix.com/docs/rest/business-management/automations/triggers/the-trigger-payload-schema) (add required fields, special annotations, etc.).
   - Enable scheduling ([how-to](https://dev.wix.com/docs/rest/business-management/automations/triggered-events/internal-creating-a-new-automations-trigger)).
   - Add SPI endpoints ([about SPI endpoints](https://dev.wix.com/docs/build-apps/develop-your-app/extensions/backend-extensions/about-service-plugin-extension)).
   - Add [filters](https://dev.wix.com/docs/rest/business-management/automations/triggers/filter-fields) to payload fields if needed.

---

## Editing Trigger Schema: What Goes Where

Auto-converted triggers are based on your proto file, but some aspects can be managed directly in Dev Center.  
*The trigger schema structure and field order are derived from your proto definition.*

---

## Proto-Based Annotations

| Annotation Name            | Description                                  |
|----------------------------|----------------------------------------------|
| Type                       | Data type of the field                       |
| Format                     | Available formats for string fields          |
| oneOf (enum)               | Field with predefined values                 |
| description                | Brief explanation of field purpose           |
| required                   | Marks the field as mandatory                 |
| futureDate                 | Allows future date/time for scheduled triggers|
| Items Selection SPI        | Enables user selection of items via SPI (any ID field should support) |
| ORDER_ID                   | Links trigger to actions that require an order ID |
| IMAGE_URL                  | Displays a dynamic image from a URL (e.g., in email content) |
| ATTACHMENT                 | Allows adding attachments via URL and filename (for email) |
| hidden                     | Hides the field from users                   |
| MONEY                      | Represents a monetary value (currency + amount)|

---

**After completing these steps, your trigger will be in draft mode and ready for testing.**

![Draft trigger created and ready for testing](../../../images/Draft%20Trigger%20created%20and%20ready%20for%20testing.png?raw=true)

---

<div align="right">

➡️ [Continue to: Test Your Trigger →](./TEST_YOUR_TRIGGER.md)

</div>
