# GitHub Research Digest

> Short digest for the team sync. All findings below were pulled **live from GitHub** at research time — no cached or historical data was used.

---

## 1. Worst-Offending Memory-Leak Report in VS Code (`microsoft/vscode`)

Among **open** issues in `microsoft/vscode` that mention "memory leak", the memory-leak report with the most thumbs-up (👍) reactions is:

| Field | Value |
|---|---|
| **Issue number** | [#294050](https://github.com/microsoft/vscode/issues/294050) |
| **Exact title** | Copilot Chat extension memory usage/leak causing frequent resets of extension host process |
| **Thumbs-up (👍) count** | **9** (as reported by GitHub at pull time) |

**Context:** The reporter shows that the GitHub Copilot Chat extension drives a VS Code process to a bit over 4 GB, causing the extension host to reset repeatedly during normal coding sessions (reproduced with all other extensions disabled). The issue is still **open**, carries the `bug` and `freeze-slow-crash-leak` labels, and has 17 comments.

**Runner-up (for reference):** [#323344](https://github.com/microsoft/vscode/issues/323344) — "[Linux][Wayland] Severe memory leak in VSCode main process on Fedora 44 (GNOME/Wayland) – persists with --disable-gpu, --disable-extensions, and fresh profile" — with **7** 👍.

> **Methodology note:** Open issues were ranked by 👍 reactions. The single highest-reaction open issue matching the phrase "memory leak" anywhere in its text (including comments) is #52116, "[Feature Request] Extension Permissions, Security Sandboxing & Update Management Proposal" — but that is an extension-permissions feature request rather than a memory-leak report, so it is excluded from the "worst-offending memory-leak report" above.

---

## 2. Where React Keeps `useSyncExternalStore` (`facebook/react`)

**File path:** `packages/react/src/ReactHooks.js`

The hook is defined and exported there alongside React's other public hooks:

```js
export function useSyncExternalStore<T>(
  subscribe: (() => void) => () => void,
  getSnapshot: () => T,
  getServerSnapshot?: () => T,
): T {
  const dispatcher = resolveDispatcher();
  return dispatcher.useSyncExternalStore(
    subscribe,
    getSnapshot,
    getServerSnapshot,
  );
}
```

Like the other hooks in this file, it resolves the current dispatcher and delegates to it; the renderer-specific implementation lives in the reconciler, but the definition of the hook itself lives in `packages/react/src/ReactHooks.js`.

---

## 3. My Organization Team Obligations

Checked the organization team membership for this GitHub account right now:

- **Organizations I belong to:** `mcpmark-eval-liuhezi`
- **Teams I'm on:** **none** — the team list for that organization is empty.

**Plainly stated: I am currently on zero organization teams, so I have no team-based responsibilities or obligations on GitHub at this time.**

---

*This digest is stored at `research/github-digest.md` in the `github-research-digest` repository so it stays versioned rather than getting lost in a chat thread.*
