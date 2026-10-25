# voice-ai-assistant-chatgpt-patch

DOM selectors for [Voice AI Assistant](https://chromewebstore.google.com/detail/voice-ai-assistant/johkmflniodnhfahiipibjlgdkemnbhd), the Chrome extension that starts ChatGPT Voice with a wake word.

ChatGPT changes its page from time to time. The extension downloads [`patch.json`](patch.json) (cached for two hours) so a broken button can be fixed here, without publishing a new extension version. No user data is sent with the request.

## Format

```json
{
  "version": "2026-10-25",
  "alpha": { "speechButton": "…", "speechButtonAlt": "…", "speechClose": "…", "speechCloseAlt": "…" },
  "v2": { "startVoice": ["…"], "endVoice": ["…"], "composer": ["…"], "send": ["…"], "readAloud": ["…"] }
}
```

- **`alpha`** is read by version 1.x: one CSS selector per key, tried with `querySelector`. Keep it valid for 1.x users.
- **`v2`** is read by version 2.0 and later: each key is a list of CSS selectors, tried in order. They are tried *before* the selectors built into the extension, so a patch can only add fixes, never remove a working one.

| Key | What it finds |
| --- | --- |
| `startVoice` | The button that starts ChatGPT Voice (only shown when the message box is empty) |
| `endVoice` | The button that ends a voice chat |
| `muteVoice` | The microphone button during a voice chat |
| `composer` | The message box (for "Type it for me") |
| `send` | The send button, shown once the message box has text |
| `readAloud` | The "Read aloud" button under each answer |
| `stopGenerating`, `loggedOut` | Optional: generation in progress, and the logged-out page |

Update `version` (a date) whenever selectors change, so users can see which fixes they have in **Settings → Troubleshooting**.

## Checking a change

In a signed-in ChatGPT tab, run in DevTools:

```js
document.querySelectorAll('button[aria-label="Start Voice"]').length // 1 when the message box is empty
```

Last verified against chatgpt.com on 2026-10-25: the signed-in app uses `aria-label` "Start Voice", "End Voice", "Turn off microphone", "Send" and "Read aloud".