# SpeechX Practice App

A fully local, single-file web app that simulates the **Tech Mahindra SpeechX Assessment**.
Designed for practice when you cannot speak aloud — **typing is the primary mode**.

---

## How to Run

1. Open `index.html` in **Google Chrome** (double-click the file, or drag it into Chrome).
2. That's it — no install, no server, no internet required.

> **Note on Mic Mode**: Web Speech API (microphone + TTS) works best in **Google Chrome**.
> If mic permission is denied or the browser doesn't support it, the app automatically falls
> back to type-only mode — it always works.

---

## Three Practice Modes

| Mode | What you do | Timer |
|------|------------|-------|
| **📖 Read Aloud** | Read/type the passage | 20 / 30 / 40 s (Hard / Medium / Easy) |
| **🎧 Listen & Repeat** | Hear a sentence once, then type or repeat it | No timer (self-paced) |
| **🎤 Extempore** | 60-second structured answer on a topic | 30 s thinking + 60 s speaking |

---

## Settings

Click ⚙️ in the top-right corner to change:
- **Input Mode**: Type Mode (default) or Mic Mode
- **Difficulty**: Easy / Medium / **Hard** (matches real SpeechX difficulty)
- **TTS Voice**: Choose from your browser's installed English voices

Settings are saved automatically and persist across sessions.

---

## Practice History

Click 📊 to open the history sidebar. The last 50 sessions are saved with
mode, difficulty, score, and timestamp — stored in your browser's localStorage.

---

## Editing Passages, Clips & Topics

All content is embedded in `index.html` in a clearly labelled JSON block:

```
<script id="app-data" type="application/json">
{
  "passages":        [ ... ],   ← 15 passages (5 Easy, 5 Medium, 5 Hard)
  "listenClips":     [ ... ],   ← 20 listen-and-repeat sentences
  "extemporeTopics": [ ... ]    ← 60 topics (12 per category)
}
</script>
```

Open `index.html` in any text editor, search for `app-data`, and edit the JSON.
Follow the existing entry format — copy an entry, change the `id`, and add your text.

### Passage entry format
```json
{
  "id": "ra_e6",
  "difficulty": "Easy",
  "text": "Your passage text here.",
  "keywords": ["important", "words", "to", "cover"]
}
```

### Extempore topic format
```json
{
  "id": "ex_w13",
  "category": "Workplace",
  "topic": "Should companies offer mental health days as paid leave?"
}
```

---

## Scoring Guide

| Score | Band | Meaning |
|-------|------|---------|
| 80–100 | 🟢 Excellent | SpeechX high-band |
| 60–79  | 🟡 Good       | Competent, minor gaps |
| 40–59  | 🟠 Needs Work | Noticeable issues |
| 0–39   | 🔴 Poor       | Significant improvement needed |

**Extempore target**: 110–140 words in 60 seconds = Score 100 on Word Count.

---

## File Structure

```
techmpractice/
├── index.html          ← The entire app (open this in Chrome)
└── README.md           ← This file
```
