# RoomWhisper ✦
### *Speak your dream space into existence*

> A multimodal AI interior design assistant that combines your room photo, your spoken emotion, and Claude's vision to generate a complete redesign concept — no designer needed.

---

## What It Does

Most people can't afford an interior designer. Most AI tools give you generic text suggestions. **RoomWhisper bridges both worlds** — you show it your actual room, tell it how you want to *feel* in that space, and it generates a full design concept in seconds.

**The three inputs:**
- 🖼 **Image** — drag & drop a photo of your real room
- 🎤 **Voice** — speak your emotional vision aloud (Web Speech API)
- 💬 **Text** — type your vibe as a fallback

**What gets generated:**
- A **poetic concept name** tailored to your room + mood
- An **evocative description** of the transformation vision
- A **custom color palette** with interactive hover swatches
- **6 mood elements** that define the atmosphere
- A **prioritized shopping guide** with estimated price ranges
- A **signature one-liner** to crystallize the whole vision

---

## Demo

```
Upload a photo → Speak or type your vibe → Click "Whisper This Room"
```

**Example prompt:**
> *"I want mornings to feel like a Parisian café — warm, cozy, a little chaotic but intentional"*

**Style chips available:** Japandi · Maximalist · Cottagecore · Industrial · Biophilic · Art Deco · Wabi-Sabi · Memphis

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML/CSS/JS — zero dependencies, single file |
| AI Vision + Language | Claude claude-sonnet-4-20250514 via Anthropic API |
| Speech Input | Web Speech API (browser-native) |
| Image Input | FileReader API + drag-and-drop |
| Hosting | GitHub Pages (static) |

---

## Setup & Usage

### Option 1 — Open locally
```bash
git clone https://github.com/01rmachani/room-whisper.git
cd room-whisper
open room-whisper.html
```

The app calls the Anthropic API directly from the browser. You'll need an **Anthropic API key** configured — see [Anthropic API docs](https://docs.anthropic.com).

> **Note:** For production use, proxy your API calls through a backend to keep your key secure. This MVP calls the API directly for simplicity.

### Option 2 — GitHub Pages (live URL)
1. Go to **Settings → Pages**
2. Set source to `main` branch
3. Your app will be live at:
   ```
   https://01rmachani.github.io/room-whisper/room-whisper.html
   ```

---

## How It Works

```
┌─────────────┐    ┌──────────────────┐    ┌────────────────────┐
│  Room Photo │    │  Spoken / Typed  │    │   Style Chip       │
│  (base64)   │ +  │  Vibe Description│ +  │   (optional)       │
└──────┬──────┘    └────────┬─────────┘    └────────┬───────────┘
       │                    │                        │
       └────────────────────┴────────────────────────┘
                            │
                    Anthropic API
               claude-sonnet-4-20250514
                 (vision + language)
                            │
              ┌─────────────▼──────────────┐
              │     Structured JSON output  │
              │  concept · palette · mood   │
              │  elements · shopping list   │
              └─────────────┬──────────────┘
                            │
                   Rendered in browser
```

---

## File Structure

```
room-whisper/
└── room-whisper.html    # Entire app — self-contained single file
└── README.md
```

---

## Why This Is Rare

| Tool | What it does | What's missing |
|---|---|---|
| Pinterest | Visual mood boards | No AI, no your actual room |
| ChatGPT | Text design advice | No vision, no structured output |
| Midjourney | Imagines new rooms | Can't analyze *your* space |
| **RoomWhisper** | All three — your room + your voice + structured plan | — |

The combination of **real room photo analysis + emotional speech input + actionable output** in a single zero-dependency file is the gap this fills.

---

## Roadmap Ideas

- [ ] Export design concept as PDF moodboard
- [ ] Save & compare multiple concepts
- [ ] Link shopping items to real product URLs
- [ ] Room-by-room history with before/after
- [ ] Share concept as a public link

---

## Built With

- [Claude API](https://docs.anthropic.com) by Anthropic
- [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) + [DM Mono](https://fonts.google.com/specimen/DM+Mono) — Google Fonts
- Web Speech API — browser native, no library needed

---

## License

MIT — do whatever you want with it.

---

*Made with Claude Sonnet · One file · Zero frameworks · All vibe*
