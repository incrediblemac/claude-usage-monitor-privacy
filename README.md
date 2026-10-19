# Privacy Policy — Claude Usage Monitor

**Last updated: October 19, 2026**

## Summary

Claude Usage Monitor is a Chrome extension that shows your Claude.ai usage limits in the toolbar, a popup, or Chrome's side panel. It reads your own usage figures from claude.ai using the login you already have in Chrome, and keeps them on your device. The developer does not collect, receive, store, or sell any of your data, and the extension contains no analytics or tracking.

## What the extension reads

While you are logged in to claude.ai, the extension reads only the following, using your existing browser session:

- **Usage data** from the claude.ai usage API (`/api/organizations/{id}/usage`): your current-session and weekly limit percentages and reset times, any additional per-model or per-product limits, lock status, this week's usage split by product (for example Claude Code or Chats), free "limit reset" grants (count, expiry date and description), and usage-credit / extra-usage status (spend, limit, balance, auto-reload, and why credits are off, if they are).
- **Credits data** from the claude.ai credits API (`/api/organizations/{id}/prepaid/credits`): your prepaid credit balance and auto-reload setting.
- **Organisation ID**, taken from the claude.ai API address so the extension can request your own usage data. It is not used for anything else.
- **Promotion banner text.** When you open the Usage section of claude.ai settings, the extension reads the text of any "limits are temporarily boosted" style promotion shown there, so it can display it in the popup. Nothing else on the page is read.

The extension never reads your conversations, prompts, files, or Claude's responses. It never reads, stores, or transmits passwords, cookies, or session tokens: requests to claude.ai are made by Chrome with your existing login, exactly as when you visit the site yourself.

## What the extension stores

Everything is stored only on your device, in Chrome's built-in extension storage:

- **`chrome.storage.local`**: the latest usage and credits data, fetch timestamps and status, the current promotion text, which alerts have already been shown (so they are not repeated), and any custom fonts you chose (cached so they work offline).
- **`chrome.storage.sync`**: your settings only (theme, fonts, refresh interval, display and notification preferences).

## Optional sync

Your settings in `chrome.storage.sync` are synced by Chrome across browsers where you are signed in to the same Google account with Chrome Sync turned on, the same way Chrome syncs bookmarks. This is handled entirely by Google's Chrome Sync. The developer has no access to it. No usage data is placed in sync storage.

## Network requests

- **claude.ai**: the only service your usage data comes from. Requests go directly from your browser to claude.ai with your own session. They are not routed through any server operated by the developer.
- **Google Fonts** (`fonts.googleapis.com`, `fonts.gstatic.com`): contacted only if you pick a custom font in settings, to download that font once. The request contains only the font name and no personal identifiers or usage data. The font is then cached locally and not downloaded again.

As with any web request, the receiving servers (claude.ai and Google) see your IP address while handling the request, under their own privacy policies. The extension sends no data to the developer or to any other party.

## Optional features

- **Side panel**: the "Open in sidebar" setting (off by default) shows the same usage view in Chrome's side panel instead of a popup. It reads no additional data.
- **Custom fonts**: off until you pick one; see Network requests above.

## Notifications

All alerts are generated locally on your device from the usage data above: usage thresholds, a limit reaching 100%, a limit resetting, pace warnings, an unused free reset about to expire, and an optional startup summary. Each one can be turned off in the extension's settings. No notification content is sent anywhere.

## Permissions

| Permission | Why |
|---|---|
| `storage` | Save usage data and settings on your device |
| `unlimitedStorage` | Let cached custom-font files exceed Chrome's default local-storage quota |
| `alarms` | Refresh usage data in the background on the schedule you choose |
| `notifications` | The optional local alerts described above |
| `sidePanel` | The optional side-panel view (off by default) |
| Host access to `https://claude.ai/*` | Read your usage data from the claude.ai API and the promotion text described above |
| Host access to `fonts.googleapis.com`, `fonts.gstatic.com` | Download a custom font, only when you choose one |

## What we do NOT do

- We do not collect, transmit, sell, or share any personal data.
- We do not read your Claude conversations, prompts, files, or outputs.
- We do not read or store passwords, cookies, or session tokens.
- We do not track your browsing or read any website other than claude.ai.
- We do not use analytics, telemetry, advertising, or third-party SDKs.
- We do not operate any server that receives your data.

## Your control

You can turn off any notification or display section in the extension's settings. Removing the extension deletes all of its locally stored data.

## Changes to this policy

If this policy changes, the updated version will be published at this same address with a revised "Last updated" date.

## Contact

Questions or concerns: open an issue in this repository, or email **fullscreendev@gmail.com**.

## About the developer

Claude Usage Monitor is built by the team behind [TechStoriesIndia.com](https://techstoriesindia.com/), covering tech news, launches and how-tos, and [TechStoriesIndia.in](https://techstoriesindia.in/), covering gadget launches, specs and buying guides.

---

*Claude Usage Monitor is an independent extension. It is not affiliated with, endorsed by, or sponsored by Anthropic. "Claude" and "Claude.ai" are trademarks of Anthropic, PBC, used here only to describe what the extension works with.*
