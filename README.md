# Voicemeeter ↔ RadioDJ MIDI Bridge

**voicemeeter‑radiodj‑midi**  
A MIDI bridge to control **VB-Audio VoiceMeeter** using MIDI input, with optional integration into **RadioDJ** automation workflows.

## 🎛️ Overview

This tool allows you to control VoiceMeeter's mixer interface via MIDI controllers—whether physical hardware (like a MIDI fader bank) or virtual sources (like loopMIDI). You can map faders, knobs, and buttons to VoiceMeeter actions such as:

- Volume (gain) control
- Mute/unmute
- Solo
- Bus routing assignments

Pair it with **RadioDJ** to create a seamless broadcast environment where MIDI can control both audio routing and playlist automation.

## 🖥️ Requirements

- **Windows** (tested on Windows 10/11)
- **VoiceMeeter** (Banana, Potato, or Basic) installed  
  👉 [https://vb-audio.com/Voicemeeter](https://vb-audio.com/Voicemeeter)
- Optional: **RadioDJ** automation system  
  👉 [https://radiodj.ro](https://radiodj.ro)
- A MIDI device (hardware or virtual like loopMIDI)

## 📦 Installation

1. Download the latest installer from the [Releases](https://github.com/theandulino/voicemeeter-radiodj-midi/releases) page.
2. Run the `.exe` installer and follow the instructions.
3. After installation, launch the application from the Start Menu or desktop shortcut.

## ⚙️ Configuration

Once installed, the app will create a configuration file on first launch (`config.json`).

You can customize MIDI mappings by editing this file, for example:

```json
{
  "midiDevice": "Your MIDI Controller",
  "mappings": [
    {
      "type": "fader",
      "cc": 10,
      "voicemeeterCommand": "Strip[0].Gain"
    },
    {
      "type": "button",
      "cc": 40,
      "on": "Strip[1].Mute = 1",
      "off": "Strip[1].Mute = 0"
    }
  ]
}
