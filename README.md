# Summer of Bitcoin 2025 – PR Tracker

Hi! I'm **Divyansh Jamwal** ([@I-lost-everytime](https://github.com/I-lost-everytime))  
Aspiring **Summer of Bitcoin 2025** contributor.

This repository tracks my open-source pull requests and learning progress.

---

## PROJECT: JoinMarket Web UI (JAM)

### PR #1 | Memory leak fix in bc-button

- **PR_LINK:** https://github.com/getAlby/bitcoin-connect/pull/360
- **STATUS:** Open
- **PROBLEM:** Store subscriptions created within the bc-button component were never cleaned up on unmount, causing memory leaks during repeated mounts and state updates.
    Over time, this could degrade performance in long-running applications using Bitcoin Connect.
- **SOLUTION:** Implemented proper unsubscribe logic using component lifecycle callbacks, ensuring subscriptions are consistently cleaned up when the component is disposed.
- **TECH:** TypeScript, Lit
- **SCOPE:** Performance


---

## PROJECT: Nostr Components

### PR #2 | npm install workaround for Storybook peer conflicts

- **PR_LINK:** https://github.com/saiy2k/nostr-components/pull/49
- **STATUS:** Open
- **PROBLEM:** Fresh clones of the repository failed during npm install due to unresolved Storybook peer dependency conflicts.
  The error originated from transitive dependencies, not application code, making the project appear broken to new contributors.
- **SOLUTION:**Documented a safe and reproducible workaround (npm install --legacy-peer-deps) in the README to unblock local development while upstream dependencies stabilize.
- **TECH:** TypeScript, Vite, Storybook
- **SCOPE:** Validation

---

### PR #3 | Keyboard accessibility for nostr-profile-badge

- **PR_LINK:** https://github.com/saiy2k/nostr-components/pull/50
- **STATUS:** Open
- **PROBLEM:** The nostr-profile-badge component relied entirely on mouse interaction, making it inaccessible to keyboard-only users and assistive technologies.
  This excluded users who navigate via keyboard and violated basic accessibility expectations for interactive identity components.
- **SOLUTION:** Implemented keyboard activation using standard key events, added proper focus handling, and resolved nested interactive element conflicts to ensure predictable behavior across input methods.
- **TECH:** TypeScript, Web Components
- **SCOPE:** Accessibility

---

## PROJECT: Zeus Wallet

### PR #4 | Windows npm install workaround

- **PR_LINK:** https://github.com/ZeusLN/zeus/pull/3437
- **STATUS:** Open
- **PROBLEM:** On Windows systems, npm install failed due to unresolved peer dependency conflicts in the React Native toolchain.
    This prevented Windows developers from building and contributing to Zeus Wallet, a production Lightning Network application.
- **SOLUTION:** Documented a stable npm install --legacy-peer-deps workaround in the README, restoring a working setup path without modifying the existing dependency graph.
- **TECH:** TypeScript, React Native, npm
- **SCOPE:** Compatibility

---

### PR #5 | Optional cross-env start script

- **PR_LINK:** https://github.com/ZeusLN/zeus/pull/3441
- **STATUS:** Open
- **PROBLEM:** NODE_ENV was set differently across Windows shells (PowerShell, CMD, Git Bash), leading to inconsistent runtime behavior and confusing environment-specific bugs during local development and
    testing.
- **SOLUTION:** Added an optional start:prod script using cross-env to provide consistent environment variable handling across platforms, without altering or breaking existing scripts.
- **TECH:** Node.js, npm, cross-env
- **SCOPE:** Compatibility

---

### PR #6 | Frontend validation for NWC inputs

- **PR_LINK:** https://github.com/ZeusLN/zeus/pull/3448
- **STATUS:** Open
- **PROBLEM:** Invalid Nostr Wallet Connect (NWC) inputs were only detected after initiating deeper flows, resulting in generic error messages that obscured the real cause of failure.
    For wallet software, delayed and unclear validation reduces user trust and increases support overhead.
- **SOLUTION:**Implemented early frontend validation using existing localized strings, allowing input issues to be detected and communicated before network or wallet operations begin.
- **TECH:** TypeScript, React Native
- **SCOPE:** Validation

---

## PROJECT: Alby / Bitcoin Connect

### PR #7 | Accessibility semantics for ResponsiveButton

- **PR_LINK:** https://github.com/getAlby/hub/pull/1992
- **STATUS:** Open
- **PROBLEM:** Icon-only buttons lacked accessible labels and proper disabled semantics, making their purpose unclear to screen-reader users and causing disabled states to be incorrectly announced.
- **SOLUTION:**Added descriptive aria-labels, applied correct aria-disabled semantics, and marked decorative icons as hidden from the accessibility tree to ensure accurate announcements by assistive technologies.
- **TECH:** TypeScript, React, ARIA
- **SCOPE:** Accessibility

---

### PR #8 | Disabled state support for nostr-follow-button

- **PR_LINK:** https://github.com/saiy2k/nostr-components/pull/52
- **STATUS:** Open
- **PROBLEM:** The follow button remained interactive during loading and unavailable states, allowing users to trigger actions that could not be completed.
   This caused inconsistent behavior for keyboard users and unclear state announcements for screen readers.
- **SOLUTION:** Implemented proper disabled-state handling by applying the disabled attribute, blocking focus when unavailable, and improving ARIA semantics to accurately reflect interaction state.
- **TECH:** TypeScript, Web Components
- **SCOPE:** Accessibility

---

### PR #9 | Investment amount validation feedback (Angor)

- **PR_LINK:** https://github.com/block-core/angor/pull/606
- **STATUS:** Open
- **PROBLEM:** Invalid investment amounts were not clearly communicated to users, resulting in silent failures or ambiguous feedback during a financial interaction.
  In investment-related flows, unclear validation increases user error and reduces confidence in the platform.
- **SOLUTION:**Added UI-level validation feedback by leveraging the existing validity state, surfacing precise and immediate error messages without modifying backend logic.
- **TECH:** C#, Avalonia UI, XAML
- **SCOPE:** Validation

---

### PR #10 | Accessibility semantics exploration (Closed)

- **PR_LINK:** https://github.com/getAlby/hub/pull/1992
- **STATUS:** Closed
- **PROBLEM:** Accessibility semantics were initially implemented at an inappropriate abstraction level, increasing complexity and making the solution harder to maintain across the component system.
- **SOLUTION:** Closed the PR after maintainer feedback, documented the learnings, and adjusted the approach in subsequent accessibility-focused contributions to apply semantics at the correct layer.
- **TECH:** TypeScript, React, shadcn/ui
- **SCOPE:** Learning

---

### PR #11 | Windows Compatibility for Dev Scripts

- **PR_LINK:** https://github.com/joinmarket-webui/jam/pull/997
- **STATUS:** Open
- **PROBLEM:**Local development for JoinMarket Web UI silently assumed a Unix shell environment.
On Windows, environment variables failed to resolve, blocking contributors at the very first setup step.
This disproportionately excluded Windows developers from contributing to a Bitcoin privacy project.
- **SOLUTION:** Replaced inline Unix-style environment variables with cross-env, ensuring scripts behave consistently across Windows, macOS, and Linux — without changing existing workflows.
- **TECH:** TypeScript, Node.js, npm, cross-env
- **SCOPE:** Compatibility
- **TESTED_ON:** Windows 10

---

### PR #12 | Accessibility & interaction refactor for bc-pay-button

- **PR_LINK:** https://github.com/getAlby/bitcoin-connect/pull/361
- **STATUS:** Open
- **PROBLEM:** The bc-pay-button relied on non-semantic div elements for user interaction, preventing reliable keyboard navigation and limiting screen-reader support in a payment-related component.
  Inaccessible payment interactions can block users entirely and reduce trust in financial tooling.
- **SOLUTION:** Refactored the component to use a semantic button element, added appropriate ARIA attributes, and introduced aria-live announcements to communicate state changes to assistive technologies.
- **TECH:** TypeScript, Lit, ARIA
- **SCOPE:** Accessibility

---

_Last updated: December 2025_
