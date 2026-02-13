
# 📦 PicoClaw

**Ultra‑Lightweight Personal AI Assistant in Go**
Runs as a tiny AI agent on ultra‑low‑resource hardware — *under 10 MB of RAM and booting in ~1 second*, even on inexpensive boards. 

---

## 🚀 What is PicoClaw?

PicoClaw is a **minimalist personal AI assistant** built in Go, designed to operate on resource-constrained Linux devices including low-cost RISC-V, ARM, and x86 boards. It’s inspired by lightweight projects like Nanobot and re-imagined from the ground up for efficiency and portability. 

* 🧠 **Ultra-Low Footprint:** Runs with less than *10 MB* resident memory. 
* 💡 **Cost-Effective:** Suitable for hardware as inexpensive as *$10*. 
* ⚡ **Fast Startup:** Ready in about *1 second* on weak single-core CPUs. 
* 🔧 **Portable:** Single self-contained binary for RISC-V, ARM, and x86. 
* 🛠 **AI-Bootstrapped:** Core mostly generated and optimized via AI-assisted tooling with human refinement.
* 🔥 **Official domain:** [picoclaw](https://picoclaw.org/)

---

## 🌟 Features

| Feature                             | Description                                                                          |
| ----------------------------------- | ------------------------------------------------------------------------------------ |
| **Low Memory Usage**                | <10 MB RAM footprint, dramatically smaller than comparable assistants. ([GitHub][1]) |
| **Broad Architecture Support**      | Works on RISC-V, ARM, x86 boards and systems. ([GitHub][1])                          |
| **Multi-Mode Operation**            | CLI interactive mode, gateway mode for messaging platforms. ([GitHub][1])            |
| **Messaging Platform Integrations** | Supports Telegram, Discord, QQ, DingTalk (via gateway). ([GitHub][1])                |
| **Configurable via JSON**           | Simple settings for providers, agents, tools, and channels. ([GitHub][1])            |
| **Command Scheduling**              | Cron support for periodic tasks/automation. ([GitHub][1])                            |

---

## 🛠️ Installation

### Precompiled Binary (Quick Start)

1. Download the appropriate binary for your platform from the **Releases** page.
2. Unpack and run:

```bash
./picoclaw agent
```

---

### From Source (Development)

```bash
git clone https://github.com/sipeed/picoclaw.git
cd picoclaw

# Dependencies
make deps

# Build locally
make build

# (Optional) Build for multiple platforms
make build-all

# Install to your system
make install
```

---

### Docker Compose (No Local Install)

1. Clone this repo.
2. Copy and edit config:

```bash
cp config/config.example.json config/config.json
vim config/config.json # set API keys, tokens, etc.
```

3. Launch services:

```bash
docker compose --profile gateway up -d
```

4. Tail logs:

```bash
docker compose logs -f picoclaw-gateway
```

5. Stop:

```bash
docker compose --profile gateway down
```

---

## 💡 Quick Start

1. **Initialize** config/workspace:

```bash
picoclaw onboard
```

2. **Configure** API keys:
   Edit `~/.picoclaw/config.json` with providers (e.g., OpenRouter, Zhipu) and messaging tokens. 

3. **Chat** via CLI:

```bash
picoclaw agent -m "Hello, PicoClaw!"
```

---

## 📱 Messaging Platforms

PicoClaw can act as a gateway-connected assistant through chat platforms:

* **Telegram** – Bot token + user allow list. 
* **Discord** – Bot token + intents. 
* **QQ** / **DingTalk** – Enable via config channels. 

> Configuration examples are included in the `config/example.json`.

---

## 🧠 Configuration Overview

A typical `~/.picoclaw/config.json` includes:

* Default agent settings (model, tokens, context limits). 
* Model provider API configuration (OpenRouter, Zhipu, etc.). 
* Tool settings (e.g., Brave Search for web lookups). 
* Messaging channel enablement + credentials. 
---

## 📦 Contributing

Contributions are welcome!

* Report bugs or feature requests via **Issues**. 
* Submit enhancements as **Pull Requests**.
* Join the community on Discord (invite link in docs). 
---

## 📜 License

Licensed under the Apache-2.0 License — see `LICENSE` for details.

---

## 🏷️ Acknowledgements

Built by **Sipeed** — enabling accessible AI on edge and embedded devices. 

