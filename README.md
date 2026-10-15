# Talk

**Chat and talk with Ternary Bonsai 2, running privately in your browser on your own GPU.**

### ▶ Try it: https://pre.bonsai.stream/

Talk is one web page. It downloads a Bonsai 2 model once, then runs it on your GPU through WebGPU. Your chats, your voice and your documents never leave your machine.

## What it does

- **Chat** with Bonsai 2B, 4B or 9B. Answers stream in with formatting, math and code highlighting.
- **Talk** hands-free: it listens, knows when you've finished speaking, answers out loud, and stops when you talk over it. The mic and the voice each have their own mute button.
- **Speech to text** of your choice (Settings): Whistle (built in, the default), or Whisper tiny.en, base.en or small.en (downloaded from Hugging Face on first use).
- **Show it pictures**: attach, paste or drop an image and ask about it.
- **Chat with your documents**: add PDF, Markdown, JSON, JSON Lines or text files. They're read and indexed in the tab, and answers cite the passages they used.
- **Look things up** on Wikipedia and DuckDuckGo, and check the **weather** (Open-Meteo). All of it is fetched straight from your browser, and it can be turned off in Settings.
- **Works offline** once a model is downloaded: with no network, it just answers from what it knows.
- Chats are saved in the browser, with Regenerate, Edit, Stop and Markdown export.

## What you need

- A browser with **WebGPU**: Chrome or Edge 113+ on Windows, macOS, ChromeOS or Android, or Safari 26 on macOS / iOS. On Linux, Chrome may need WebGPU enabled in `chrome://flags`.
- A GPU with enough free memory for the model you pick. The download is cached, so it happens only once.

| Model | Download, model + vision | Good for |
|---|---|---|
| [Bonsai 2B](https://huggingface.co/prism-ml/Ternary-Bonsai-2-2B-gguf) | 0.43 GB + 0.36 GB | phones, laptops with integrated graphics |
| [Bonsai 4B](https://huggingface.co/prism-ml/Ternary-Bonsai-2-4B-gguf) | 0.95 GB + 0.37 GB | most laptops and desktops |
| [Bonsai 9B](https://huggingface.co/prism-ml/Ternary-Bonsai-2-9B-gguf) | 2.0 GB + 0.62 GB | desktops and laptops with a discrete GPU |

The weights come from Hugging Face (`prism-ml`). If Hugging Face can't be reached, Talk uses the Prism ML mirror instead. You can also download a GGUF yourself and open it with **Open model file**.

## Privacy

- No cookies, no analytics, no telemetry, and no chat logs.
- Chats, settings and documents live in your browser's storage.
- Speech recognition and speech synthesis run in the tab.
- The only network requests go to the page host, the model download, and (when you use them) Wikipedia, DuckDuckGo and Open-Meteo.

Details are in [PRIVACY.md](PRIVACY.md). Answers come from a small AI model running on your machine, so they can be wrong. Check anything important yourself.

## What's in this repo

| Path | What it is |
|---|---|
| `talk.html` | the whole app in one file: page, chat logic and the GPU engine, compressed and packed |
| `kernels.ts` | the readable source of the WebGPU engine that runs Bonsai 2 (GGUF reader, tokenizer, WGSL kernels, vision). `talk.html` is built from this exact file |
| `assets/voice/` | the voice models and their runtimes: Silero VAD, Smart Turn v3.2, Whistle, Paradee-8M, ONNX Runtime Web, Transformers.js |
| `assets/pdf/` | PDF.js, for reading PDF documents |
| `assets/fonts/`, `assets/katex/` | fonts |
| `LICENSE`, `NOTICE`, `PRIVACY.md` | license, third-party credits and license texts, privacy |

## Hosting it yourself

Talk is static. Any web server that serves the files in this repo works:

```sh
git clone https://github.com/PrismML-Eng/Talk && cd Talk
python3 -m http.server 8000
# then open http://localhost:8000/talk.html
```

It has to be served over `http://localhost` or `https://`, not opened as a `file://` page, because WebGPU and the voice workers need a secure context. No special headers are needed.

## Credits

Built by [Prism ML](https://prismml.com). The WebGPU engine is ported from the [webml-community Ternary Bonsai 2 WebGPU kernels](https://huggingface.co/spaces/webml-community/ternary-bonsai-2-webgpu-kernels). Voice: [Whistle](https://huggingface.co/Cactus-Compute/whistle) by Cactus Compute, [Paradee-8M](https://huggingface.co/sahilmahendrakar/Paradee-8M-v1.0), [Silero VAD](https://github.com/snakers4/silero-vad), [Smart Turn](https://github.com/pipecat-ai/smart-turn), [misaki](https://github.com/hexgrad/misaki) and [Whisper](https://huggingface.co/onnx-community). Page: marked, KaTeX, highlight.js, DOMPurify and PDF.js. Weather data by [Open-Meteo.com](https://open-meteo.com/). The full list with licenses is in [NOTICE](NOTICE).

## License

[Apache License 2.0](LICENSE).
