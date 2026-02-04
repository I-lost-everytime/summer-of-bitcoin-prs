# Summer of Bitcoin 2025 – PR Tracker

Hi! I'm **Divyansh Jamwal** (GitHub: [@I-lost-everytime](https://github.com/I-lost-everytime)),  
an aspiring **Summer of Bitcoin 2025** contributor.

This repository tracks my open-source contributions, pull requests, and learning progress during the application phase.

---

## 🟢 JoinMarket Web UI (JAM)

### PR #1 – Windows Compatibility for Dev Scripts

- **PR Link:** https://github.com/joinmarket-webui/jam/pull/997  
- **Status:** Open  
- **Problem:** Development scripts used Unix-style environment variables, breaking setup on Windows  
- **Solution:** Replaced inline env vars with `cross-env` for cross-platform compatibility david
- **Tech:** TypeScript, Node.js, npm, cross-env  
- **Tested On:** Windows 10 

---

## 🟢 Nostr Components

### PR #2 – npm install workaround for Storybook peer conflicts

- **PR Link:** https://github.com/saiy2k/nostr-components/pull/49  
- **Status:** Open  
- **Problem:** `npm install` failed with `ERESOLVE` errors due to Storybook peer dependency constraints  
- **Solution:** Documented `npm install --legacy-peer-deps` workaround in README  
- **Tech:** TypeScript, Vite, Storybook  

---

### PR #3 – Keyboard accessibility for `nostr-profile-badge`

- **PR Link:** https://github.com/saiy2k/nostr-components/pull/50  
- **Status:** Open (Review in progress)  
- **Problem:** Profile badge was mouse-only and inaccessible to keyboard users  
- **Solution:**  
  - Added keyboard activation (Enter + Space)  
  - Added focus handling & `:focus-visible` styles  
  - Prevented nested interactive element conflicts  
- **Concepts:** Accessibility (WCAG), keyboard navigation, event delegation  
- **Tech:** TypeScript, Web Components  

---
### PR #4 – Windows npm install workaround for ZEUS

- **PR Link:** https://github.com/ZeusLN/zeus/pull/3437

- **Status:** Open

- **Problem:** npm install fails on Windows due to peer dependency conflicts

- **Solution:**   Documented npm install --legacy-peer-deps workaround in README

- **Tech:**  TypeScript, React Native, npm

- **Tested on:**  Windows 10

### PR #5 – Add optional cross-env start script for Windows compatibility

- **PR Link:** https://github.com/ZeusLN/zeus/pull/3441

- **Status:** Open

- **Problem:**
 Environment variables like NODE_ENV are not consistently supported across Windows shells (PowerShell / CMD)
 This causes confusion when running development scripts on Windows

- **Solution:** 

Added an opt-in start:prod script using cross-env

Ensures consistent environment variable handling across platforms

No existing scripts or workflows were modified

- **Tech:**  Node.js, npm/yarn scripts, cross-env

- **Scope:** Minimal, non-breaking developer experience improvement

### PR #6 – Frontend validation for Nostr Wallet Connect inputs

- **PR Link:**https://github.com/ZeusLN/zeus/pull/3448

- **Status:** Open

- **Related Issue:** https://github.com/ZeusLN/zeus/issues/3442

### PR #7 – Improve accessibility and disabled semantics in Alby Hub ResponsiveButton

- **PR Link:** https://github.com/getAlby/hub/pull/1992
- **Status:** Open
- **Problem:** Icon-only buttons lacked accessible labels and disabled state semantics, especially on smaller screens and when composed with `asChild`
- **Solution:**  
  - Added accessible labeling for icon-only buttons  
  - Ensured `aria-disabled` is set when disabled  
  - Marked decorative icons as `aria-hidden`
- **Tech:** TypeScript, React, Accessibility (ARIA)
- **Scope:** Minimal, non-breaking UI correctness improvement

### PR #8 – Add disabled state support to `nostr-follow-button`

- **PR Link:** https://github.com/saiy2k/nostr-components/pull/52  
- **Status:** Open  

- **Problem:**  
  The `nostr-follow-button` component did not support a disabled state, allowing interaction during loading or when follow actions were unavailable. This caused accidental interactions and reduced accessibility for keyboard and screen-reader users.

- **Solution:**  
  - Added support for a `disabled` attribute  
  - Blocked interaction and keyboard focus when disabled  
  - Applied appropriate ARIA attributes (`role="button"`, `aria-disabled`, `aria-pressed`)  
  - Improved keyboard navigation and screen-reader feedback  

- **Concepts:**  
  Accessibility (ARIA), keyboard interaction, UI state safety  

- **Tech:**  
  TypeScript, Web Components, Nostr UI components  

- **Scope:**  
  Minimal, non-breaking UI & accessibility improvement  



- **Problem:**
Invalid inputs during Nostr Wallet Connect setup (e.g. empty connection name or missing permissions) were only caught late in the flow, often resulting in generic or hard-to-debug error messages.

- **Solution:**
Added early, frontend-level validation for NWC connection inputs to surface clear, localized error messages before attempting connection creation.

Reused existing validation locale strings

Added validation at a shared submission point

Improved UX without touching connection or Lightning logic

- **Tech:**  TypeScript, React Native

- **Scope:** Minimal, frontend-only validation improvement  

### PR #9 – Investment Amount Validation Feedback (Angor)

 **PR Link:**: https://github.com/block-core/angor/pull/606

 **Status:** Open

**Problem:**
Invalid investment amounts (e.g. zero or empty input) were not clearly communicated to users during the investment flow, leading to confusion and poor UX.

**Solution:** 
Added UI-level validation feedback that displays a clear error message when the entered investment amount is invalid, using existing validation state (IsValid).

**Tech:**
C#, Avalonia UI, XAML

 **Scope:**
UI-only improvement
No changes to transaction logic, wallet logic, or protocol behavior

**Why it matters:**
Improves user confidence and reduces friction for first-time investors by providing immediate, actionable feedback.

### PR #10– Accessibility semantics exploration for ResponsiveButton (Alby Hub)

**PR Link:**: https://github.com/getAlby/hub/pull/1992

 **Status:** Closed (by author after maintainer review)

**Problem:**
Icon-only buttons in ResponsiveButton lacked clear accessibility semantics (labeling and disabled state handling), especially when composed using asChild.

**Solution Attempted:**

Added accessible labeling for icon-only buttons

Ensured aria-disabled is set when disabled

Marked decorative icons as aria-hidden

**Maintainer Feedback:**
Accessibility semantics should live in the underlying shadcn/ui Button, not in the ResponsiveButton wrapper, which is intentionally thin.

**Outcome:**
PR was closed by the author after discussion, with agreement to move accessibility improvements to the correct abstraction layer.

**Concepts:**
Accessibility (ARIA), component architecture, abstraction boundaries

**Tech:**
TypeScript, React, shadcn/ui

**Scope:**
Exploratory PR / learning-focused (no merge)

### PR #11 – Memory leak fix: Store subscription cleanup in `bc-button`

- **PR Link:** [https://github.com/getAlby/bitcoin-connect/pull/360](https://github.com/getAlby/bitcoin-connect/pull/360)
- **Status:** Open (All checks passed ✅)
- **Problem:** `bc-button` was subscribing to the global store without ever unsubscribing. This leads to memory leaks and unnecessary background processing when the component is removed and re-added to the DOM.
- **Solution:** - Captured the `unsubscribe` function returned by `store.subscribe`.
  - Implemented the `disconnectedCallback` lifecycle method to properly clean up the listener.
  - Refactored state synchronization to be more robust.
- **Tech:** TypeScript, Lit, State Management (Redux-style store)
- **Scope:** Performance & Stability
### PR #12  – Accessibility & Interaction Refactor: bc-pay-button
- **PR Link:** https://github.com/getAlby/bitcoin-connect/pull/361

- **Status:** Open (All checks passed ✅)

- **Problem:** The payment button used a non-semantic div wrapper for click events, making it inaccessible to keyboard users and screen readers during critical financial transactions.

- **Solution:** - Refactored component to use the core <bci-button> for all interactions.

Implemented dynamic aria-label to provide audio feedback for "Loading" and "Paid" states.

Added aria-live="polite" to announce status changes automatically.

Enabled native disabled attribute handling to prevent double-payments and improve UX.

- **Tech:**TypeScript, Lit, Web Components, ARIA

- **Scope:** Accessibility & Financial Safety




## 🟡 Upcoming Contributions

- Nostr Components – further UI & accessibility improvements  
- Zeus Wallet – UX / developer-experience improvements  
- Rust-based org (VLS) – test coverage & beginner-friendly Rust fixes
   

---

## 📌 Notes

- Focused on small, meaningful, well-tested PRs  
- Actively responding to maintainer & CodeRabbit feedback  
- Learning Rust and Bitcoin internals alongside JavaScript / TypeScript  

_Last updated: December 2025_
