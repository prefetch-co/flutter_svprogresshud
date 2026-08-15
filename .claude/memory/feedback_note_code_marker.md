---
name: feedback_note_code_marker
description: Never add NOTE CODE markers on my own — the user adds them manually; only place one when the user explicitly asks
metadata:
  type: feedback
---

**Never add `NOTE CODE` markers automatically.** The user writes them manually.

Only place a marker when the user explicitly asks for it in the request.

**Format (when asked):** `NOTE CODE <KEY>` where `<KEY>` is 8 characters drawn from `A-Z a-z 0-9`, written in **uppercase** (e.g. `K7XQ9M2P`). The key comes from the user, never from me.

**Comment syntax must match the language of the file:**

```ts
// NOTE CODE K7XQ9M2P
const value = ...;
```

**Placement (when asked):**
- Put the marker directly above the changed code.
- One marker per changed position; contiguous changes share a single marker.
- If the changed code already has a comment (JSDoc or block comment), put the `NOTE CODE` line at the **top of that comment**.

**Why:** The user marks changed positions themselves; markers added by me are noise and had to be stripped out of a whole module.

**How to apply:** Do not write `NOTE CODE` anywhere unless the user asked for it. Applies to all repos on this machine.
