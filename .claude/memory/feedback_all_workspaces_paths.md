---
name: feedback_all_workspaces_paths
description: "\"all workspaces\", \"other 3 repos\" and similar always mean these 4 paths: evcnx, prefetch, explore, gather"
metadata:
  type: feedback
---

When the user says **"apply for all workspaces"**, **"in all workspaces"**, **"other 3 repo(s)"**, **"in other 3 repos"**, or any similar wording, it always means these 4 workspace paths:

- `/Users/tnitsiri/Documents/evcnx`
- `/Users/tnitsiri/Documents/prefetch`
- `/Users/tnitsiri/Documents/explore`
- `/Users/tnitsiri/Documents/gather`

Each workspace holds several repos (`console`, `console-api`, `app`, `app-api`, `asset`, `common`, …).

**Why:** The user works across these 4 workspaces at once and expects the same change applied in every one of them. Guessing a different set, or asking which paths are meant, wastes their time.

**How to apply:**

1. Treat those 4 paths as the full scope — do not ask which workspaces are meant.
2. "Other 3 repos" = the 3 workspaces other than the current one.
3. Search every workspace for the same pattern before reporting "clean" — see [[feedback_only_do_what_is_ordered]] for staying inside the ordered scope while doing so.
4. Report per workspace, and still stop and wait when the user only asked a question — see [[feedback_answer_then_stop]].
