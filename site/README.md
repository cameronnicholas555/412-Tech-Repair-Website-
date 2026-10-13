# 412 Tech Repair

Unpublished website built with Next.js App Router, TypeScript, Tailwind CSS, and Lucide icons.

## Preview on your computer

Use Node.js 20.9 or newer (Node.js 22 LTS recommended):

```sh
npm ci
npm run dev
```

Open http://localhost:3000. To view on a phone or tablet connected to the same trusted Wi-Fi, run `npm run dev -- --hostname 0.0.0.0`, then open `http://YOUR_COMPUTER_LAN_IP:3000` on the device. Stop the server with Ctrl+C.

## Checks and static build

```sh
npm run typecheck
npm run build
```

`out/` contains the static site. This can use inexpensive static hosting when you are ready to publish. Nothing has been deployed.

## Pages

Home `/`, services `/services/`, about `/about/`, contact `/contact/`, quote demo `/request-repair/`.

## Demo and real business details

The quote form validates required fields, email format, contact availability, and phone format. It displays an explicit demo completion message; no network request, database write, local storage, notification, or real submission occurs. Use fictional information when previewing. Returning from the completion screen resets the form.

`src/lib/business.ts` holds the phone number and Facebook URL. Until real details are supplied, the call/text/Facebook controls are disabled and labeled. No prices, testimonials, address, hours, or repair time guarantees have been invented.

## Future dashboard

See ARCHITECTURE.md. There is deliberately no public dashboard placeholder or simulated authentication.
