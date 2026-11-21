# Pocket Terminal

<p>
  <a href="https://pocket-terminal-concept.pages.dev/"><img src="https://img.shields.io/badge/Live_Demo-F38020?style=flat&logo=cloudflare&logoColor=white" alt="Live Demo" /></a>
  <img src="https://img.shields.io/badge/Svelte-5.56-FF3E00?style=flat&logo=svelte&logoColor=white" alt="Svelte 5.56" />
  <img src="https://img.shields.io/badge/TypeScript-6.0-3178C6?style=flat&logo=typescript&logoColor=white" alt="TypeScript 6.0" />
  <img src="https://img.shields.io/badge/Three.js-0.187-000000?style=flat&logo=threedotjs&logoColor=white" alt="Three.js 0.187" />
  <img src="https://img.shields.io/badge/Hugging_Face_Transformers-4.2-FCC624?style=flat&logo=huggingface&logoColor=white" alt="Hugging Face Transformers 4.2" />
  <img src="https://img.shields.io/badge/ONNX_Runtime-005CED?style=flat&logo=onnx&logoColor=white" alt="ONNX Runtime" />
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-8A8A8A?style=flat&logo=github&logoColor=white" alt="License: MIT" /></a>
</p>

**Visual and interactive concept / prototype.** A personal terminal in the form of a pocket device, rendered entirely in the browser. It is not an emulator or a general-purpose app: it's a UX and design exploration of what a terminal GUI would feel like inside a physical gadget — housing, navigation rail and glass screen — built only with web technologies.

Each app behaves like a terminal session, with its own prompt (`pgomur@iphone ~ %`) and everything shown as text, with no native widgets.

| Soft Skeuo | Glass Optical | Retro CRT |
| :---: | :---: | :---: |
| <img src="docs/screenshots/soft-skeuo.webp" alt="Soft Skeuo: white soft-plastic device with a graphite active key, showing the Chat app" /> | <img src="docs/screenshots/glass-optical.webp" alt="Glass Optical: frosted glass device on a misty blue background with a blue active key, showing the Clock app" /> | <img src="docs/screenshots/retro-crt.webp" alt="Retro CRT: beige device with an amber active key and a green phosphor CRT screen, showing the Game of Life" /> |

## Apps

- **Chat**: Qwen3-0.6B running 100% in your browser on WebGPU (or WASM as a fallback), with no server and no external API. The model downloads only when you ask for it and stays cached for later visits, replies stream token by token and an optional thinking mode reasons before answering. Type `/help` to see every command.
- **Clock**: a drift-free clock with day, week, month and year progress bars, ISO week number, day of year and Unix time.
- **Bitcoin**: live price and 24h metrics from CoinGecko with a 7-day chart drawn on the terminal's character grid, refreshed every minute.
- **Life**: Conway's Game of Life that keeps itself alive — rotating seeds, cycle and stagnation detection, and live metrics including Shannon entropy.
- **System**: the real device and browser behind the screen: OS, browser, GPU, CPU cores, memory, screen, WebGPU support and more.

## Themes and 3D view

Three themes, switchable instantly from the selector in the top-right corner: **Soft Skeuo** (soft white plastic), **Glass Optical** (frosted glass over a misty blue background) and **Retro CRT** (beige plastic and a green phosphor tube).

An optional **3D view** rebuilds the device in Three.js, with modelled keys and materials matched to each theme, while the screen stays live and selectable. Drag outside the device to rotate it; on Android phones it also follows the gyroscope.

The device adapts to any screen size, from desktop to phone, and is fully keyboard accessible: arrow keys move between apps, `1`–`5` open them directly and every theme shows a clear focus outline.

## Known limitations

- The chat model is small (0.6B parameters) so it can run in the browser: it's a local-inference experiment, not a reliable assistant.
- In System, memory and JS heap rely on Chromium-only APIs and show as unavailable in Firefox and Safari.
- The Bitcoin data comes from CoinGecko's public API, which is rate-limited.
- The 3D view needs WebGL 2; without it the device stays in the flat view.
- Apart from the selected theme and view, nothing is saved: the chat and the Game of Life start over on reload.

> **Source:** [Private Repo](https://github.com/pgomur/pocket-terminal-concept-priv)
