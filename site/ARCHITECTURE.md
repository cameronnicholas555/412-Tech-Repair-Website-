# Future business management

Current source separates App Router pages (`src/app`), reusable UI (`src/components`), business configuration (`src/lib`), and repair contracts (`src/types`). Static export keeps the initial site small and inexpensive; no paid APIs, remote fonts, or database are needed.

When connecting the backend:

1. Add a server deployment or separate API and remove `output: "export"` if using Next.js route handlers/server features.
2. Use managed authentication with staff roles and server-side authorization on every dashboard page and API. Route groups can separate `(marketing)` and `(dashboard)` layouts, but grouping alone does not secure access.
3. Introduce customer, device, repair, repair-event, inventory-item, inventory-movement, payment-reference, and notification-job tables. Relate repairs to customers/devices and record status changes with timestamps and staff attribution.
4. Validate and normalize form input on the server, rate-limit requests, add abuse prevention, and show success only after durable storage. Provide a privacy notice and consent where relevant before accepting real data.
5. Store secrets only in server environment variables. Use parameterized queries, least-privilege database access, audit trails, backups, and clear retention policies.
6. Use a payment provider's hosted checkout. Store provider references rather than card details; verify webhook signatures and handle retries idempotently.
7. Send notifications through a retryable server queue after confirmed events, with customer preferences and delivery records.

Future customer tracking should use authenticated access or expiring unguessable tokens, with server authorization that prevents access to another customer's records. Do not place customer data or credentials in static output or browser storage.

These are integration plans, not implemented business management features.
