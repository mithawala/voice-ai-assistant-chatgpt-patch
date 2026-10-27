# voice-ai-assistant-chatgpt-patch

DOM selectors for [Voice AI Assistant](https://chromewebstore.google.com/detail/voice-ai-assistant/johkmflniodnhfahiipibjlgdkemnbhd), the Chrome extension that starts a voice chat with ChatGPT or Microsoft Copilot, or hands a task to Copilot Cowork, when you say a wake word.

The assistants change their pages from time to time. The extension downloads [`patch.json`](patch.json) (cached for two hours) so a broken button can be fixed here, without publishing a new extension version. No user data is sent with the request.

## Format

```json
{
  "version": "2026-10-27",
  "alpha": { "speechButton": "…", "speechButtonAlt": "…", "speechClose": "…", "speechCloseAlt": "…" },
  "v2": { "startVoice": ["…"], "endVoice": ["…"], "composer": ["…"], "send": ["…"], "readAloud": ["…"] },
  "providers": {
    "chatgpt": { "startVoice": ["…"], "endVoice": ["…"], "composer": ["…"], "send": ["…"] },
    "copilot": { "startVoice": ["…"], "endVoice": ["…"], "composer": ["…"], "send": ["…"] }
  }
}
```

- **`alpha`** is read by version 1.x (ChatGPT only): one CSS selector per key, tried with `querySelector`. Keep it valid for 1.x users.
- **`v2`** is read by version 2.0 (ChatGPT only). Keep it valid for 2.0 users.
- **`providers`** is read by version 2.1 and later: one block per assistant (`chatgpt`, `copilot`; `cowork` from 2.2, and later `gemini`). For ChatGPT it wins over `v2`. Cowork has no voice chat, so its block only has the task box, the send button and the signed-out page.

In `v2` and `providers`, each key is a list of CSS selectors, tried in order. They are tried *before* the selectors built into the extension, so a patch can only add fixes, never remove a working one.

| Key | What it finds |
| --- | --- |
| `startVoice` | The button that starts the assistant's voice chat |
| `endVoice` | The button that ends a voice chat |
| `muteVoice` | The microphone button during a voice chat |
| `composer` | The message box (for "Type it for me") |
| `send` | The send button, shown once the message box has text |
| `readAloud` | The "Read aloud" button under each answer (ChatGPT) |
| `replyText` | An answer's text, read aloud with the browser's voice when there's no "Read aloud" button (Copilot) |
| `stopGenerating`, `loggedOut`, `loggedOutText` | Optional: an answer being written, and the signed-out page |
| `dismissNotices` | The start of the title of the assistant's notifications that are harmless and get closed as soon as they appear (ChatGPT: `Silero VAD failed to load`). Only notifications are touched, never the chat |
| `noticeToast`, `noticeClose` | A notification and its close button |

Update `version` (a date) whenever selectors change, so users can see which fixes they have in **Settings → Troubleshooting**.

## Checking a change

In a signed-in tab, run in DevTools:

```js
// ChatGPT (chatgpt.com), message box empty
document.querySelectorAll('button[aria-label="Start Voice"]').length // 1
// Copilot (Microsoft 365 Copilot, copilot.cloud.microsoft), message box empty
document.querySelectorAll('button[aria-label="Start a new voice chat"]').length // 1
```

Last verified on 2026-10-27:

- **chatgpt.com** (signed in): `aria-label` "Start Voice", "End Voice", "Turn off microphone", "Send" and "Read aloud".
- **Microsoft 365 Copilot** (copilot.cloud.microsoft, work account): "Start a new voice chat", "End voice chat" (`data-testid="End Realtime Conversation"`), "Mute", "Send", "Stop generating"; the message box is `#m365-chat-editor-target-element` ("Message Copilot"); answers are `[data-testid="copilot-message-reply-div"]`.
- **Copilot Cowork** (copilot.cloud.microsoft/cowork, work account): the task box is a `span[role="textbox"]` with `aria-label` "Chat input" ("Start a task…" on the home page, "Message Cowork" in a task); "Send" appears once it has text (before that the button is "Start dictation"). Tasks open at `/cowork#/task/<id>`. Signed out, /cowork is a landing page whose "Try Cowork" button (`#cowork-hero-cta`) links to /login. Verified end to end: a spoken task typed into a new task and sent, and a follow-up into the open task.
- Personal Copilot (copilot.microsoft.com) wasn't checked; the extension also tries common labels for it ("Talk to Copilot", "Submit message", `textarea#userInput`).
