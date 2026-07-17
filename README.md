# ⌨️ Typing Dojo

A clean, self-contained browser game that teaches you to **touch-type fast** — structured lessons, timed practice, an arcade mode, and progress tracking. No build step, no dependencies, no account. It's a single HTML file that runs fully offline.

> Open `index.html` in any browser and start typing.

---

## ✨ Features

### 🎓 Learn
A 12-lesson ladder that builds touch-typing from the ground up: home row → top row → bottom row → all letters → common words → capitals → numbers → punctuation → sentences → speed run. Each lesson unlocks the next.

- An **on-screen keyboard** highlights the next key to press.
- Every key is **tinted by the finger** that should press it (pinky, ring, middle, index, thumb), so you learn correct hand position.
- The home-row keys (**F** and **J**) are marked, just like the bumps on a real keyboard.
- Wrong keys flash, and each lesson ends with your WPM, accuracy, a star rating, and the keys you missed.

### ⏱️ Practice
A Monkeytype-style speed test for building raw speed.

- Pick **15 / 30 / 60 seconds**, with live WPM and accuracy.
- Your **personal best per duration** is saved.
- A **"Focus on my weak keys"** mode pulls in the letters you miss most.

### 🎮 Challenge — Word Rush
A minimal arcade mode for the fun/replay hook.

- Type each word before the shrinking timer bar empties.
- It speeds up as you go; streaks and level-ups build your score.
- Three lives, and a saved high score.

### 📊 Stats
- Best WPM, lifetime accuracy, time practiced, and a **day streak**.
- A per-key **error heatmap** showing exactly which keys trip you up.

### 🎨 Polish
- **Light / dark theme toggle** that overrides your OS setting and remembers your choice.
- Respects `prefers-reduced-motion` and `prefers-color-scheme`.
- All progress is saved locally in your browser.

---

## 🚀 Getting started

### Option 1 — just open it
Download or clone the repo and double-click **`index.html`**. That's it. It works entirely offline.

```bash
git clone https://github.com/absharma2794/typing-dojo.git
cd typing-dojo
open index.html          # macOS  (use "start" on Windows, "xdg-open" on Linux)
```

### Option 2 — serve it over HTTP
Some browsers behave a little more consistently over `http://` than `file://`. Any static server works:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

A ready-made config lives in [`.claude/launch.json`](.claude/launch.json).

---

## ⌨️ Keyboard shortcuts

| Key | Action |
|-----|--------|
| Any character | Type the highlighted character |
| `Backspace` | Correct the previous character |
| `Esc` | Restart the current run (lesson / practice / challenge) |

---

## 🔒 Data & privacy

Everything runs client-side. Your progress, stats, personal bests, and theme choice are stored in your browser's `localStorage` — nothing is ever sent anywhere. There are **no network calls** at all. Use the **Reset all progress** button on the Stats tab to wipe it.

---

## 🛠️ How it works

- **One file, vanilla everything.** All HTML, CSS, and JavaScript live in `index.html` — no frameworks, no bundler, no `node_modules`.
- **Theming** via CSS custom properties, with a `data-theme` attribute overriding the `prefers-color-scheme` default.
- **A small typing engine** consumes keystrokes and tracks index, correctness, timing, and a per-key error map, emitting live metrics (WPM = correct chars ÷ 5 ÷ minutes; accuracy = correct ÷ total keystrokes).
- **Word and quote pools** are embedded as JavaScript arrays.

### Project structure

```
typing-dojo/
├── index.html          # the entire app
├── .claude/
│   └── launch.json     # optional static-server config for local preview
├── .gitignore
└── README.md
```

---

## 🤝 Contributing

Bug fixes and features are developed on the `developement` branch and merged into `main` via pull request. To hack on it, edit `index.html` and reload the page — there's nothing to build.

---

*Built as a self-contained learning tool. Have fun getting faster. 🥋*
