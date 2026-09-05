---
name: confluent-webhook-notifications
description: >-
  Register a webhook (or Slack / Microsoft Teams) delivery target for Confluent Cloud
  platform notifications, verify delivery, and subscribe it to the notification types
  that matter. Use to get Confluent Cloud events out to an external system.
api: openapi/confluent-the-data-streaming-platform-cloud-apis-openapi.yml
base_url: https://api.confluent.cloud
operations:
  - listNotificationsV1NotificationTypes
  - createNotificationsV1Integration
  - testNotificationsV1Integration
  - listNotificationsV1Integrations
  - createNotificationsV1Subscription
  - createNotificationsV1ResourceSubscription
  - deleteNotificationsV1Integration
---

# Wire Confluent Cloud notifications to a webhook

## Steps

1. `listNotificationsV1NotificationTypes` — `GET /notifications/v1/notification-types`.
   The event catalog is served at runtime, not in the contract. Enumerate it; never
   hard-code an event name.
2. `createNotificationsV1Integration` — `POST /notifications/v1/integrations` with a
   target. `notifications.v1.WebhookTarget` takes `webhook_url`; Slack and MsTeams
   targets take their own incoming-webhook URLs. `RoleEmail` integrations are managed by
   Confluent and cannot be created, updated or deleted through this API.
3. `testNotificationsV1Integration` — `POST /notifications/v1/integrations:test`.
   **Do this before subscribing.** It is supported only for Webhook, Slack and MsTeams,
   and it is the only delivery proof the API offers.
4. `createNotificationsV1Subscription` — bind notification types to the integration.
   Use `createNotificationsV1ResourceSubscription` to scope to one resource instead of
   the whole org.

## Verifying inbound payloads

The contract documents **no** signing secret, HMAC signature header or replay window for
Confluent-originated deliveries. A receiver cannot verify authenticity from the contract
alone — use a hard-to-guess path with a shared secret in the URL, restrict by source, and
treat the payload as untrusted input.

## Reversal

`deleteNotificationsV1Integration` removes the target and stops delivery. Notifications
that already fired are not recalled.
