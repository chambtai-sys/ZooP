# ZooP Desktop

ZooP is an **advanced desktop collaboration client** designed as a next-generation Zoom companion experience.

It is built to connect to Zoom infrastructure using official Zoom integrations (OAuth, Zoom APIs, and SDK-based meeting/video capabilities), while adding a richer desktop UX layer for power users.

> **Important note**
> ZooP is an independent project concept and is **not** an official Zoom product.

---

## ZooP 1.0 Release

**Version:** `1.0.0`  
**Channel:** Desktop-first (Windows, macOS, Linux)

### What ships in 1.0

- Native-feeling desktop shell for meetings and collaboration workflows.
- Zoom account sign-in flow via OAuth 2.0.
- Meeting lifecycle support (schedule, join, leave, and post-meeting summaries).
- Team workspace panel for quick access to recurring rooms and contacts.
- Session enhancements:
  - AI-powered meeting notes (local + cloud pipeline ready).
  - Smart mute reminders and speaking-time insights.
  - One-click scene/layout presets for presentations.
- Security baseline:
  - Encrypted token storage.
  - Role-aware permission checks.
  - Audit-friendly activity event logging.

---

## Product Vision

ZooP aims to be the "pro desktop layer" over real-time communication:

- **Faster meeting operations:** keyboard-first navigation and command palette.
- **Better context:** pre-meeting briefings and in-meeting action capture.
- **Cleaner post-meeting outcomes:** automatic summary generation, action item extraction, and follow-up triggers.

---

## High-Level Architecture

ZooP Desktop uses a modular architecture:

1. **Desktop App Layer**
   - Electron or Tauri shell
   - React/Vue UI
   - Native system integrations (notifications, tray, global shortcuts)

2. **Collaboration Core**
   - Session orchestration
   - Participant state model
   - Layout and media-control engine

3. **Zoom Integration Layer**
   - OAuth 2.0 login and refresh token workflow
   - Zoom REST API client (users, meetings, recordings, webhooks)
   - Zoom SDK bridge for in-call media and controls

4. **Data + Intelligence Layer**
   - Local encrypted cache
   - Optional cloud sync
   - Notes/summaries/tasks extraction pipeline

---

## Connecting to Zoom Servers

ZooP connects to Zoom servers through official interfaces:

- **Authentication:** Zoom OAuth app credentials.
- **API access:** Zoom REST endpoints for scheduling/user/meeting operations.
- **Real-time meeting integration:** Zoom Meeting SDK / Video SDK modules.
- **Events:** Webhooks for meeting updates and post-meeting automation.

To enable connectivity:

1. Create a Zoom app in the Zoom Developer Portal.
2. Configure redirect URIs for desktop OAuth flow.
3. Store `ZOOM_CLIENT_ID`, `ZOOM_CLIENT_SECRET`, and callback URL.
4. Complete OAuth consent and token exchange.
5. Use access token in ZooP integration services.

---

## Desktop Experience (Core UX)

- **Command Palette** (`Ctrl/Cmd + K`) for instant actions.
- **Dockable Panels** (chat, participants, notes, tasks).
- **Focus Modes** (Presenter, Discussion, Deep Work).
- **Smart Window Management** for multi-monitor meeting setups.
- **System Tray Presence** with quick join/mute/camera toggles.

---

## Suggested Repository Layout

```text
zoop/
  apps/
    desktop/
  packages/
    ui/
    core/
    zoom-adapter/
    ai-notes/
  services/
    api/
    webhook-worker/
  docs/
    architecture/
    security/
```

---

## Security & Compliance Baseline

- Encrypt sensitive tokens at rest using OS keychain facilities.
- Keep least-privilege OAuth scopes.
- Redact personally identifiable data in logs by default.
- Add explicit user consent before recording or transcription.

---

## 1.0 Release Checklist

- [x] Product scope and architecture defined.
- [x] Desktop-first interaction model defined.
- [x] Zoom connectivity approach documented.
- [x] Security baseline documented.
- [ ] SDK integration implementation.
- [ ] Production build + installer pipeline.
- [ ] End-to-end QA on Windows/macOS/Linux.

---

## Quick Start (Implementation Plan)

1. Bootstrap desktop shell (`apps/desktop`).
2. Implement OAuth login screen and token manager.
3. Add Zoom meetings list + join flow.
4. Add in-call controls and layout presets.
5. Add notes + summary pipeline.
6. Prepare `v1.0.0` installer and release assets.

---

## License

Choose a license before public distribution (MIT/Apache-2.0 recommended for open source).
