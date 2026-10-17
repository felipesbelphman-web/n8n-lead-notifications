# Lead Notifications — Setup

1. Use a dedicated Supabase demo project. Run schema.sql after reviewing it. For an existing contacts table, check column types and the identity sequence name first.
2. Import lead-notifications.json into n8n. The template is inactive.
3. Connect your own Supabase OAuth credential in Save contact to Supabase and replace YOUR_SUPABASE_PROJECT_REF with your project reference. Select the contacts table and verify the name, service, message and priority mappings.
4. Connect your own Microsoft Outlook OAuth credential in Send Outlook notification. Replace YOUR_EMAIL@example.com with the notification recipient you intend to use.
5. Open Receive contact form and test with fictional data. Exact case-sensitive service Online store produces High priority; another service such as Landing page produces Normal.
6. Check that both contacts are stored, and only the High contact triggers the email node. Check the mailbox and Junk folder.
7. Publish only after your own tests pass.

## Validation and limits

The original workflow was manually tested for High and Normal branches. This sanitized export was checked for valid JSON and connection targets, but has not been reimported or executed. Credentials, project reference, recipient and instance identifiers were removed or replaced; node versions and business rules were retained. The email node was renamed to match the screenshot.

The original test email was received but initially went to Junk. It was manually moved to Inbox; Outlook still showed an unverified-sender warning. Delivery authentication remains unresolved.

The confirmation message is stored, not emailed to the form visitor. This is a portfolio demonstration without deduplication, advanced validation or dedicated error handling. It is not a complete production service.

## GitHub assets

workflow.png is included. Add it to README.md with:

![Lead notification workflow](workflow.png)

The Outlook screenshot is omitted because the supplied image contains personal email addresses. Hide those addresses before uploading email-notification.png, while retaining the delivery warning.
