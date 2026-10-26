# Privacy Policy

_Last updated: 26 October 2026_

Voice AI Assistant is a Chrome extension that lets you talk to ChatGPT or Microsoft Copilot hands-free using a wake word. It does not collect, sell or share personal data.

Voice AI Assistant is an independent extension. It is not made, affiliated with or endorsed by OpenAI or Microsoft. ChatGPT is a trademark of OpenAI; Microsoft Copilot and Bing are trademarks of Microsoft.

## What happens to your voice

- While listening is on, the extension uses your browser's built-in speech recognition (the Web Speech API) to hear your wake words, your end word and, if you use them, your spoken requests. The browser performs the recognition with its speech service.
- The extension does not record, store or transmit your audio or transcripts anywhere else. Recognized words are used immediately and then discarded.
- When you use **Type it for me**, the words you say after the wake word are typed into the chat you chose (ChatGPT or Copilot) and sent, exactly as if you had typed them. That assistant's own privacy policy applies to what you send to it.
- Voice conversations take place on the assistant's own website (chatgpt.com, or Copilot's site) under your account there.
- **Read replies aloud** for Copilot uses your browser's text-to-speech on the answer shown on the page.

## What is stored

- Your settings (wake words, which assistants are on, where they open, sounds and similar preferences) are stored with `chrome.storage`. Chrome may sync them across your own signed-in browsers. They are never sent to the developer.

## Network requests

- To keep up with changes to the assistants' websites, the extension downloads a small static file, [`patch.json`](https://github.com/mithawala/voice-ai-assistant-chatgpt-patch/blob/main/patch.json), from GitHub. No user data is included in this request. See GitHub's [Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).
- Voice searches open Google Search or Bing with your spoken query, if you turn those features on.

## Permissions

- **Access to chatgpt.com**: to start and end ChatGPT Voice, type your spoken requests into the chat, and show status messages on the page.
- **Access to Copilot's sites** (copilot.microsoft.com, copilot.com, copilot.cloud.microsoft and m365.cloud.microsoft), only if you turn Copilot on: the same, for Copilot. Turning Copilot off removes this access again.
- **Microphone** (asked once by Chrome): to hear your wake words. You can turn listening off at any time from the toolbar button or with Alt+M.
- **Offscreen document**: lets the extension listen in the background without keeping a tab open.
- **Text-to-speech**: to read Copilot's answers aloud, if you turn that on.
- **Storage** and **scripting**: to save your settings and to connect to chat tabs that were open before the extension was installed or Copilot was turned on.

## Contact

Questions: [mithawala.com](https://mithawala.com).
