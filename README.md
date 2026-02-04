# Summer of Bitcoin 2025 – PR Tracker

Hi! I'm **Divyansh Jamwal** ([@I-lost-everytime](https://github.com/I-lost-everytime))  
Aspiring **Summer of Bitcoin 2025** contributor.

This repository tracks my open-source pull requests and learning progress.

---

## PROJECT: JoinMarket Web UI (JAM)

### PR #1 | Windows Compatibility for Dev Scripts

- **PR_LINK:** https://github.com/joinmarket-webui/jam/pull/997
- **STATUS:** Open
- **PROBLEM:** Development scripts relied on Unix-style environment variables, which broke setup on Windows.
- **SOLUTION:** Replaced inline environment variables with `cross-env` to ensure cross-platform compatibility.
- **TECH:** TypeScript, Node.js, npm, cross-env
- **SCOPE:** Compatibility
- **TESTED_ON:** Windows 10

---

## PROJECT: Nostr Components

### PR #2 | npm install workaround for Storybook peer conflicts

- **PR_LINK:** https://github.com/saiy2k/nostr-components/pull/49
- **STATUS:** Open
- **PROBLEM:** npm install failed due to Storybook peer dependency conflicts.
- **SOLUTION:** Documented `npm install --legacy-peer-deps` workaround in README.
- **TECH:** TypeScript, Vite, Storybook
- **SCOPE:** Validation

---

### PR #3 | Keyboard accessibility for nostr-profile-badge

- **PR_LINK:** https://github.com/saiy2k/nostr-components/pull/50
- **STATUS:** Open
- **PROBLEM:** Profile badge was mouse-only and inaccessible to keyboard users.
- **SOLUTION:** Added keyboard activation, focus handling, and prevented nested interactive conflicts.
- **TECH:** TypeScript, Web Components
- **SCOPE:** Accessibility

---

## PROJECT: Zeus Wallet

### PR #4 | Windows npm install workaround

- **PR_LINK:** https://github.com/ZeusLN/zeus/pull/3437
- **STATUS:** Open
- **PROBLEM:** npm install failed on Windows due to peer dependency conflicts.
- **SOLUTION:** Documented legacy-peer-deps workaround in README.
- **TECH:** TypeScript, React Native, npm
- **SCOPE:** Compatibility

---

### PR #5 | Optional cross-env start script

- **PR_LINK:** https://github.com/ZeusLN/zeus/pull/3441
- **STATUS:** Open
- **PROBLEM:** NODE_ENV handling differed across Windows shells, confusing developers.
- **SOLUTION:** Added optional `start:prod` script using cross-env without modifying existing workflows.
- **TECH:** Node.js, npm, cross-env
- **SCOPE:** Compatibility

---

### PR #6 | Frontend validation for NWC inputs

- **PR_LINK:** https://github.com/ZeusLN/zeus/pull/3448
- **STATUS:** Open
- **PROBLEM:** Invalid NWC inputs were caught late, leading to generic error messages.
- **SOLUTION:** Added early frontend validation using existing locale strings.
- **TECH:** TypeScript, React Native
- **SCOPE:** Validation

---

## PROJECT: Alby / Bitcoin Connect

### PR #7 | Accessibility semantics for ResponsiveButton

- **PR_LINK:** https://github.com/getAlby/hub/pull/1992
- **STATUS:** Open
- **PROBLEM:** Icon-only buttons lacked accessible labels and disabled semantics.
- **SOLUTION:** Added aria-labels, aria-disabled, and hid decorative icons.
- **TECH:** TypeScript, React, ARIA
- **SCOPE:** Accessibility

---

### PR #8 | Disabled state support for nostr-follow-button

- **PR_LINK:** https://github.com/saiy2k/nostr-components/pull/52
- **STATUS:** Open
- **PROBLEM:** Follow button allowed interaction while loading or unavailable.
- **SOLUTION:** Added disabled attribute, blocked focus, and improved ARIA semantics.
- **TECH:** TypeScript, Web Components
- **SCOPE:** Accessibility

---

### PR #9 | Investment amount validation feedback (Angor)

- **PR_LINK:** https://github.com/block-core/angor/pull/606
- **STATUS:** Open
- **PROBLEM:** Invalid investment amounts were not clearly communicated to users.
- **SOLUTION:** Added UI-level validation feedback using existing validity state.
- **TECH:** C#, Avalonia UI, XAML
- **SCOPE:** Validation

---

### PR #10 | Accessibility semantics exploration (Closed)

- **PR_LINK:** https://github.com/getAlby/hub/pull/1992
- **STATUS:** Closed
- **PROBLEM:** Accessibility semantics were implemented at the wrong abstraction level.
- **SOLUTION:** PR closed after maintainer feedback; learnings documented.
- **TECH:** TypeScript, React, shadcn/ui
- **SCOPE:** Learning

---

### PR #11 | Memory leak fix in bc-button

- **PR_LINK:** https://github.com/getAlby/bitcoin-connect/pull/360
- **STATUS:** Open
- **PROBLEM:** Store subscriptions were never cleaned up, causing memory leaks.
- **SOLUTION:** Implemented proper unsubscribe logic using lifecycle callbacks.
- **TECH:** TypeScript, Lit
- **SCOPE:** Performance

---

### PR #12 | Accessibility & interaction refactor for bc-pay-button

- **PR_LINK:** https://github.com/getAlby/bitcoin-connect/pull/361
- **STATUS:** Open
- **PROBLEM:** Non-semantic divs prevented keyboard and screen-reader access.
- **SOLUTION:** Refactored to semantic button with aria-live announcements.
- **TECH:** TypeScript, Lit, ARIA
- **SCOPE:** Accessibility

---

_Last updated: December 2025_
