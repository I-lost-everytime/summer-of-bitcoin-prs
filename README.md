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
- **Solution:** Replaced inline env vars with `cross-env` for cross-platform compatibility  
- **Tech:** TypeScript, Node.js, npm, cross-env  
- **Tested On:** Windows 10  

---

## 🟢 Nostr Components

### PR #2 – npm install workaround for Storybook peer conflicts

- **PR Link:** https://github.com/saiy2k/nostr-components/pull/49  
- **Status:** Open  
- **Problem:** `npm install` failed with ERESOLVE errors due to Storybook peer dependency constraints  
- **Solution:** Documented `npm install --legacy-peer-deps` workaround in README  
- **Tech:** TypeScript, Vite, Storybook  

### PR #3 – Keyboard accessibility for profile badge *(in progress / review)*

- **Focus:** Accessibility improvements (keyboard navigation & focus styles)
- **Concepts:** WCAG, focus-visible, event delegation
- **Status:** Under review

---

## 🟡 Upcoming Contributions

- Nostr Components – additional UI accessibility improvements
- Zeus Wallet – UX / developer experience improvement
- Rust-based org (VLS) – test coverage & small fixes

---

## 📌 Notes

- Focused on small, meaningful, well-tested PRs  
- Actively engaging with maintainer feedback & reviews  
- Learning Rust and Bitcoin internals alongside JavaScript / TypeScript  

_Last updated: December 2025_
