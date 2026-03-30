# Zamio - Mobile App for Zammad Helpdesk

<p align="center">
  <img src="https://zamio.kaju.pl/assets/appicon.png" alt="Zamio" width="120" />
</p>

<p align="center">
  <a href="https://apps.apple.com/app/zamio-kaju/id6759985715">
    <img src="https://zamio.kaju.pl/assets/appstore.svg" alt="Download on the App Store" height="50" />
  </a>
  <a href="https://play.google.com/store/apps/details?id=com.myprosoft.zamio">
    <img src="https://zamio.kaju.pl/assets/googleplay.svg" alt="Get it on Google Play" height="50" />
  </a>
</p>

<p align="center">
  <a href="https://zamio.kaju.pl">Website</a> &bull;
  <a href="#features">Features</a> &bull;
  <a href="#push-notifications">Push Notifications</a> &bull;
  <a href="#getting-started">Getting Started</a> &bull;
  <a href="#faq">FAQ</a>
</p>

---

**Zamio** is a native mobile app for [Zammad](https://zammad.com) helpdesk — available on iOS and Android. Manage your tickets, reply to customers, and get instant push notifications when something needs your attention.

## Features

### Push Notifications
Get **native push notifications** on your phone when tickets are updated. No more checking the browser — Zamio alerts you instantly so you can respond faster.

- Notifications for new tickets and updates in your groups
- Works in background, even when the app is closed
- Smart filtering — you won't get notified about your own actions

### Ticket Management
- Browse ticket overviews (My Assigned, Open, Closed, etc.)
- Filter by status and priority
- Create and edit tickets on the go
- Search tickets

### Conversations
- Read and reply to customer messages
- Add internal notes
- Attach files
- View full ticket history

### Other
- **Multi-language**: English, German, Polish, French, Spanish, Portuguese, Dutch, Ukrainian
- **Dark mode**: Follows your device settings
- **Multiple servers**: Connect to different Zammad instances
- **Secure**: API token stored in device keychain (iOS Keychain / Android Keystore)

## Push Notifications

Push notifications require a one-time setup by your Zammad administrator. The architecture is simple:

```
Zammad  --(webhook)-->  Zamio Relay Server  --(push)-->  Your Phone
```

### Setup (Admin)

1. Go to [notification.zamio.kaju.pl/setup.html](https://notification.zamio.kaju.pl/setup.html)
2. Enter your Zammad server URL and choose an HMAC secret
3. Copy the generated webhook URL
4. In Zammad: **Manage > Webhook** — create a new webhook with the URL and signature token
5. In Zammad: **Manage > Trigger** — create a trigger that fires the webhook on ticket changes

Detailed instructions with screenshots are available at [zamio.kaju.pl](https://zamio.kaju.pl) in the FAQ section.

## Getting Started

1. Install Zamio from the [App Store](https://apps.apple.com/app/zamio-kaju/id6759985715) or [Google Play](https://play.google.com/store/apps/details?id=com.myprosoft.zamio)
2. Enter your Zammad server URL (e.g. `https://support.yourcompany.com`)
3. Create an API token in Zammad: **Avatar > Profile > Token Access** (requires `ticket.agent` permission)
4. Paste the token in Zamio — you're in!

> **Note:** If you don't see Token Access in your profile, ask your Zammad admin to enable it in **Settings > System > API**.

## FAQ

**Which Zammad versions are supported?**
Zamio works with Zammad 6.0+ and uses the standard REST API (`/api/v1`). Older versions may work but are not officially tested.

**Is my data safe?**
Zamio connects directly to your Zammad server. The only external service involved is the push notification relay, which only receives webhook payloads needed to route notifications. Your API token never leaves your device. See our [Privacy Policy](https://zamio.kaju.pl/privacy.html).

**I'm not receiving push notifications**
1. Make sure your Zammad admin has completed the [webhook setup](#setup-admin)
2. Check that notifications are enabled in your device settings
3. Toggle push notifications off and on in Zamio settings

**Can I use multiple Zammad servers?**
Yes. Log out and log in with a different server URL. Push notifications follow your current login.

## Feedback & Issues

This repository serves as the **public issue tracker** for Zamio. The app source code is not included here.

- Found a bug? [Open a bug report](../../issues/new?template=bug_report.md)
- Have an idea? [Request a feature](../../issues/new?template=feature_request.md)
- General questions? [Start a discussion](../../discussions)

You can also reach us at **kontakt@kaju.pl**.

## Links

- Website: [zamio.kaju.pl](https://zamio.kaju.pl)
- App Store: [Zamio on App Store](https://apps.apple.com/app/zamio-kaju/id6759985715)
- Google Play: [Zamio on Google Play](https://play.google.com/store/apps/details?id=com.myprosoft.zamio)
- Zammad: [zammad.com](https://zammad.com)

---

Made by [Kaju](https://zamio.kaju.pl)
