# ⚙️ SHARVIS
### The Ultimate Cross-Platform Personal AI Assistant — By Sharon TN ⚡

> 🔗 **[GitHub Repository](https://github.com/Sharon-TN/SHARVIS)**

A real-time voice AI that can hear, see, speak, and control your computer — across Windows, macOS, and Linux. Built on the Gemini Live API for native bidirectional audio streaming, delivering zero subscriptions, lightning-fast response times, and total digital autonomy.

---

## ✨ Overview

**SHARVIS is an advanced AI assistant featuring a real-time holographic face avatar.** A holographic head sits at the centre of the HUD and **speaks your assistant's words with real lip-sync** — generating true anatomical mouth shapes in real-time (lips closing on *m*, *b*, *p*, spreading on *i*, rounding on *u*). Eyebrows track sentence dynamics, eyes make natural saccadic fixation movements, and it blinks intuitively.

It ships with **zero heavy 3D rendering dependencies** and a lightweight 25 KB geometry asset. The face is real measured human geometry; the rest of the rig and dynamic lighting are generated at startup and rendered entirely in software with PyQt6 QPainter — ensuring identical, ultra-smooth performance on high-end desktop workstations and older laptops alike, without GPU or driver conflicts.

The avatar also doubles as an instant status indicator:
- **Looking away**: Thinking and processing
- **Direct eye contact**: Actively listening
- **Lids closed**: Sleep / Standby mode

Under the hood, SHARVIS dynamically discovers its operating system, hardware devices, capabilities, limits, and installed plugins at session start — keeping its context fresh and accurate without hardcoded prompts.

---

## 🚀 Capabilities & Features

### Core Highlights

| Feature | Description |
|---|---|
| 🧑‍🎤 **Holographic Avatar** | Real-time 3D animated human head in the HUD — software-rendered via PyQt6 QPainter with no OpenGL/GPU dependency |
| 👄 **Dynamic Lip-Sync** | ~50 mouth shapes per second derived from audio formants and live text phonetics |
| 🌍 **Universal Articulation** | Unicode reduction pipeline supporting multi-language articulation across Latin, Cyrillic, Greek, and other scripts |
| 🙂 **Expressive Acting** | Context-driven brow movement, natural eye saccades, blinking, and vocal-emphasis head tilts |
| 🎚️ **Push-to-Talk** | Hold **Ctrl+Space** for instant microphone activation |
| 🎙️ **Wake Word** | Offline local wake word detection with automatic sleep timeout |
| 🔇 **Self-Echo Guard** | Acoustic echo suppression preventing the assistant from hearing or interrupting its own voice output |
| ⚡ **Instant Acknowledgment** | Contextual immediate voice feedback when initiating complex background tasks |
| 🚀 **Gemini Live Engine** | Powered by Google Gemini Live API for ultra-low latency, bidirectional streaming |
| 🧩 **Extensible Plugin System** | Drop single `.py` scripts into `plugins/` for instant auto-discovery on startup |
| 🧠 **Intelligent Memory** | Persistent long-term memory with local retrieval for preferences, projects, and personal notes |
| ↩️ **Safety & Undo** | Ability to revert file modifications, renames, and setting adjustments |
| ⚠️ **Explicit Confirmation** | Sensitive operations (shutdown, reboot, network disconnect) require manual user confirmation |
| 🎧 **Audio Hardware Selection** | Dynamic input/output device selector with live hardware latency measurement |
| 🎨 **Live HUD Theming** | Dynamic colour palette wheel retinting HUD rings, waveforms, and avatar lighting in real time |
| 📱 **Cross-Platform Mobile App** | Companion Android APK and mobile controller built with Kivy |
| 🌐 **Web & System Control** | Full browser automation, app launching, window manipulation, and live screen capture analysis |

---

## 🛠️ Project Structure

```text
SHARVIS/
├── actions/                  # Auto-discovered system & automation skills
│   ├── background_monitor.py # News & topic background watcher
│   ├── browser_control.py    # Playwright-powered browser automation
│   ├── code_helper.py        # Code execution & debugging helper
│   ├── computer_control.py   # Mouse, keyboard, and screen automation
│   ├── computer_settings.py  # Volume, brightness, WiFi, and power settings
│   ├── desktop.py            # Desktop environment control
│   ├── dev_agent.py          # Autonomous multi-step development agent
│   ├── file_processor.py     # Document reading, analysis, and processing
│   ├── flight_finder.py      # Live flight search
│   ├── game_updater.py       # Game launcher & updater automation
│   ├── open_app.py           # Native application launcher
│   ├── proactive.py          # Proactive check-in and situational engine
│   ├── reminder.py           # OS-native scheduled reminders
│   ├── screen_processor.py   # Screen capture & webcam vision analysis
│   ├── system_monitor.py     # CPU, RAM, GPU telemetry
│   ├── weather_report.py     # Live weather forecasting
│   ├── web_search.py         # Multi-mode search (Grounded & DDG)
│   └── youtube_video.py      # YouTube search and transcript analysis
├── android-app/              # Native Android application source (Gradle / Java)
├── config/                   # Configuration, icons, and API credentials
│   ├── api_keys.example.json # Example configuration file
│   └── sharvis.ico           # Application icon
├── core/                     # Assistant core architecture
│   ├── action_loader.py      # Dynamic action discovery engine
│   ├── audio_devices.py      # Audio hardware device manager
│   ├── avatar.py             # Holographic software avatar renderer
│   ├── avatar_mesh.py        # 3D facial geometry and vertex transforms
│   ├── echo.py               # Acoustic echo cancellation guard
│   ├── gesture_tracker.py    # Hand gesture & pointer tracking
│   ├── llm_client.py         # Gemini Live API streaming client
│   ├── plugin_loader.py      # Modular plugin engine
│   ├── prompt.txt            # Dynamic system instruction prompt
│   ├── viseme.py             # Real-time phoneme-to-viseme engine
│   └── wake_word.py          # OpenWakeWord offline detection
├── dashboard/                # Remote web control dashboard & mobile gateway
├── memory/                   # Long-term memory & configuration managers
├── plugins/                  # User plugins directory
├── main.py                   # Main desktop assistant runtime
├── ui.py                     # PyQt6 Holographic HUD & Interface
├── mobile_app.py             # Kivy mobile client
├── test_sharvis.py           # Component test suite
├── requirements.txt          # Python dependency specifications
└── setup.py                  # One-time automated environment setup
```

---

## ⚡ Quick Start

### 1. Prerequisites

- **Python 3.11+**
- A Google Gemini API Key (Available from [Google AI Studio](https://aistudio.google.com/))

### 2. Installation

Clone your repository and navigate into the project directory:

```bash
git clone https://github.com/Sharon-TN/SHARVIS.git
cd SHARVIS
```

Run the automated setup script to install all required dependencies:

```bash
python setup.py
```

Or install dependencies manually via `pip`:

```bash
pip install -r requirements.txt
```

### 3. Configuration

Configure your Gemini API key in `config/api_keys.json` (or copy from `config/api_keys.example.json`):

```json
{
    "gemini_api_key": "YOUR_GEMINI_API_KEY",
    "assistant_name": "SHARVIS",
    "user_name": "Sir",
    "voice_name": "Charon",
    "hud_style": "face",
    "wake_word_enabled": false,
    "push_to_talk_enabled": false
}
```

You can also configure your API key, voice, and assistant name directly inside the UI settings drawer (⚙️) on first launch.

### 4. Running the Tests

To verify that all modules, actions, audio devices, and memory systems are functional:

```bash
python test_sharvis.py
```

### 5. Launching SHARVIS

Start the desktop assistant:

```bash
python main.py
```

On Windows, you can also double-click `run.bat`.

---

## 🎮 Controls & Shortcuts

| Shortcut | Action |
|---|---|
| **Ctrl + Space** | Push-to-Talk (Hold to speak, release to send) |
| **F4** | Mute / Unmute microphone |
| **F11** | Toggle Fullscreen Holographic HUD |
| **Escape** | Close settings / overlay panels |

---

## 📱 Mobile Edition (Android)

SHARVIS includes a companion Android client located in the `android-app/` folder and `mobile_app.py`.
- **Pre-compiled APK**: Ready-to-install `Sharvis.apk` is available in the root folder.
- **Build from source**: Run `./build_apk.sh` on Linux / Google Colab or open the `android-app/` project in Android Studio.

---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE) — Copyright (c) 2026 Sharon TN.
