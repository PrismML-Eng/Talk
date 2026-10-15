# Privacy and terms

Talk is a single web page. The models run in your browser tab, on your own GPU. There is no Talk server and no account.

## What stays on your device

- **Your chats, settings, attached pictures and documents** are stored only in your browser (`localStorage` and IndexedDB on this site). They are never uploaded. "Delete all chats" in the side panel, the Delete buttons in Documents, or clearing your browser's site data removes them.
- **Your voice** is turned into text in the tab (Whistle or Whisper). No audio leaves your device.
- **Downloaded model files** are kept in the browser's cache so the next visit starts faster. You can delete them from the model card.

## No cookies, no telemetry

Talk sets no cookies, runs no analytics and sends no usage reports or chat logs to Prism ML or anyone else.

## What the page downloads, and from where

Your browser connects to these services. Each one sees your IP address and the request, as with any website, under its own privacy policy:

| Service | When | What is sent |
|---|---|---|
| GitHub Pages (github.io) | opening the page | a normal page request. GitHub may log IP addresses: [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) |
| Hugging Face (huggingface.co) | loading a Bonsai model, or a Whisper voice model | file downloads only: [Hugging Face privacy policy](https://huggingface.co/privacy) |
| Prism ML mirror (pre.bonsai.stream) | only if Hugging Face can't be reached | file downloads only. The mirror keeps no chat data, because it never receives any |
| Wikipedia (wikipedia.org) | when the model looks something up, if Search is on | the search words or the page title: [Wikimedia privacy policy](https://foundation.wikimedia.org/wiki/Policy:Privacy_policy) |
| DuckDuckGo (api.duckduckgo.com) | when the model looks something up, if Search is on | the search words: [DuckDuckGo privacy policy](https://duckduckgo.com/privacy) |
| Open-Meteo (open-meteo.com) | when you ask about the weather | the place name and its coordinates: [Open-Meteo terms](https://open-meteo.com/en/terms) |

Search and weather can be turned off in Settings. With them off, and the model already downloaded, Talk works with no network at all.

## AI output

The answers are written by a small language model running on your machine. They can be wrong, out of date or made up, even when they cite a source. They are not medical, legal, financial or other professional advice. Check anything important yourself.

## Terms

Talk is provided "AS IS", without warranties or conditions of any kind, under the [Apache License 2.0](LICENSE). Third-party components and services keep their own licenses and terms ([NOTICE](NOTICE)). Use it responsibly and lawfully.

Questions: open an issue at https://github.com/PrismML-Eng/Talk/issues.
