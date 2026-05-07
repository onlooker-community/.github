# Security Policy

## Project Status

Onlooker is currently an early-stage open source project maintained in limited spare time. We take security seriously but want to be honest about our capacity to respond.

---

## Reporting a Vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Email **security@onlooker.dev** with:
- Which repository and component is affected
- A description of the vulnerability
- Steps to reproduce if you have them
- Your assessment of severity

We will acknowledge receipt as soon as we can and work on a fix based on severity. We do not have formal SLAs at this stage — critical issues affecting user data will be prioritized, lower severity issues will be addressed as time allows.

---

## Scope

Most relevant to report:

- The Onlooker daemon — anything affecting local data, the sync transport, or config handling
- The sync API (`api.onlooker.dev`) — authentication, account data isolation
- Marketplace plugins — anything that could cause unexpected code execution or data exfiltration from a developer's machine
- Prompt injection bypasses in Warden

Less urgent (still welcome, just lower priority):

- Theoretical vulnerabilities without a practical exploit path
- Issues in third-party dependencies (report upstream; let us know if it affects us directly)
- Issues that require physical access to a developer's machine

---

## Privacy Note

The daemon handles developer session telemetry. `redact_content = true` in the config strips prompt content before events leave your machine. The sync server forwards events to your account without storing content beyond what's needed for delivery.

If you discover something that could expose developer session data or prompt content, that's the highest priority thing to report.
