# Privacy Policy

_Last updated: 25 October 2026_

Voice AI Assistant is a Chrome extension that lets you talk to ChatGPT hands-free using a wake word. It does not collect, sell or share personal data.

## What happens to your voice

- While listening is on, the extension uses Chrome's built-in speech recognition (the Web Speech API) to hear your wake word, your end word and, if you use them, your spoken requests. Chrome performs the recognition with its speech service.
- The extension does not record, store or transmit your audio or transcripts anywhere else. Recognized words are used immediately and then discarded.
- When you use **Type it for me**, the words you say after the wake word are typed into the ChatGPT chat you chose and sent, exactly as if you had typed them. ChatGPT's own privacy policy applies to what you send to ChatGPT.
- ChatGPT Voice conversations take place on chatgpt.com under your ChatGPT account.

## What is stored

- Your settings (wake words, where ChatGPT opens, sounds and similar preferences) are stored with `chrome.storage`. Chrome may sync them across your own signed-in browsers. They are never sent to the developer.

## Network requests

- To keep up with changes to the ChatGPT website, the extension downloads a small static file, [`patch.json`](https://github.com/mithawala/voice-ai-assistant-chatgpt-patch/blob/main/patch.json), from GitHub. No user data is included in this request. See GitHub's [Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).
- Voice searches open Google Search with your spoken query, if you turn that feature on.

## Permissions

- **Access to chatgpt.com**: to start and end ChatGPT Voice, type your spoken requests into the chat, and show status messages on the page.
- **Microphone** (asked once by Chrome): to hear your wake word. You can turn listening off at any time from the toolbar button or with Alt+M.
- **Offscreen document**: lets the extension listen in the background without keeping a tab open.
- **Storage** and **scripting**: to save your settings and to connect to ChatGPT tabs that were open before the extension was installed.

## Contact

Questions: [mithawala.com](https://mithawala.com).