# Privacy Policy

_Last updated: 28 October 2026_

Voice AI Assistant is a Chrome extension that lets you talk to ChatGPT or Microsoft Copilot hands-free using a wake word, and hand tasks to Copilot Cowork by voice. It does not collect, sell or share personal data.

Voice AI Assistant is an independent extension. It is not made, affiliated with or endorsed by OpenAI or Microsoft. ChatGPT is a trademark of OpenAI; Microsoft Copilot and Bing are trademarks of Microsoft.

## What happens to your voice

- While listening is on, the extension uses your browser's built-in speech recognition (the Web Speech API) to hear your wake words, your end word and, if you use them, your spoken requests. The browser performs the recognition with its speech service.
- The extension does not record, store or transmit your audio or transcripts anywhere else. Recognized words are used immediately and then discarded.
- When you use **Type it for me**, the words you say after the wake word are typed into the chat you chose (ChatGPT or Copilot) and sent, exactly as if you had typed them. That assistant's own privacy policy applies to what you send to it.
- When you say your Cowork wake word ("Hey Cowork" by default) and a task, your words are typed into Copilot Cowork, as a new task or in the task you have open, and sent, exactly as if you had typed them. Cowork is part of Microsoft 365 Copilot, and Microsoft's terms for your work or school account apply to what you send to it.
- Voice conversations take place on the assistant's own website (chatgpt.com, or Copilot's site) under your account there.
- **Read replies aloud** presses the page's own read-aloud button when it has one (ChatGPT). Otherwise, as on Copilot, your browser's text-to-speech reads the answer shown on the page.

## What is stored

- Your settings (wake words, which assistants are on, where they open, sounds and similar preferences) are stored with `chrome.storage`. Chrome may sync them across your own signed-in browsers. They are never sent to the developer.
- While Chrome is open, the extension also remembers the address of the last chat with each assistant (so it can continue that chat) and which windows it opened (so it can close them). This is cleared when Chrome closes and never leaves your computer.

## Network requests

- To keep up with changes to the assistants' websites, the extension downloads a small static file, [`patch.json`](https://github.com/mithawala/voice-ai-assistant-chatgpt-patch/blob/main/patch.json), from GitHub. No user data is included in this request. See GitHub's [Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).
- Voice searches open Google Search or Bing with your spoken query, if you turn those features on.

## Permissions

- **Access to chatgpt.com**: to start and end ChatGPT Voice, type your spoken requests into the chat, and show status messages on the page.
- **Access to Copilot's sites** (copilot.microsoft.com, copilot.com, copilot.cloud.microsoft and m365.cloud.microsoft), only if you turn Copilot on: the same, for Copilot.
- **Access to copilot.cloud.microsoft**, only if you turn Cowork on: to type your spoken tasks into Copilot Cowork, send them, and show status messages there.
- Turning Copilot or Cowork off removes its access again, except copilot.cloud.microsoft while the other one is still on.
- **Microphone** (asked once by Chrome): to hear your wake words. You can turn listening off at any time from the toolbar button or with Alt+M.
- **Offscreen document**: lets the extension listen in the background without keeping a tab open.
- **Text-to-speech**: to read answers aloud when the page has no read-aloud button of its own (Copilot), if you turn that on.
- **Storage** and **scripting**: to save your settings and to connect to chat tabs that were open before the extension was installed or Copilot or Cowork was turned on.

## Contact

Questions: [mithawala.com](https://mithawala.com).
