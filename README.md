<div align="center">

# 🍂 Trailside

### · on-device nature field guide

Snap something on the trail. Get field notes. Save the moment in your LogBook.

<br/>

[![Hacktoberfest 2026](https://img.shields.io/badge/Hacktoberfest-2026-f97316?style=for-the-badge&logo=hacktoberfest&logoColor=white)](https://hacktoberfest.com/)
[![Week 1 Challenge](https://img.shields.io/badge/Week-1-7c3aed?style=for-the-badge)](https://dev.to/challenges)
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![Ollama](https://img.shields.io/badge/Ollama-local_AI-000000?style=for-the-badge&logo=ollama&logoColor=white)](https://ollama.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

<br/>

[![GitHub Repo](https://img.shields.io/badge/GitHub-Gavinduachintha%2FLookout-2a2118?style=for-the-badge&logo=github)](https://github.com/Gavinduachintha/Lookout)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

<br/>

```
   🌤️   ·  ☁️        ☁️
        ╲  │  ╱
    ～～～ 🍁 🍂 🍁 ～～～     ←  you, the curious naturalist
        ╱  │  ╲
   🌲🌲🌲🌲🌲🌲🌲🌲🌲🌲
```

*Built for **[Hacktoberfest 2026 · Week 1](https://hacktoberfest.com/)** on DEV — autumn vibes, real code, zero fluff.*

</div>

---

## 📖 Table of contents

- [What you can do](#-what-you-can-do)
- [What you'll need](#-what-youll-need)
- [Quick start](#-quick-start)
- [Project layout](#-project-layout)
- [How it works](#-how-it-works)
- [Safety note](#-safety-note)
- [Hacktoberfest & contributing](#-hacktoberfest--contributing)
- [Troubleshooting](#-troubleshooting)
- [Author](#-author)

---

## ✨ What you can do

<table>
<tr>
<td width="50%" valign="top">

**📷 Capture**
- Camera or upload (JPG, PNG, WebP)
- Optional hint text for the model
- Polaroid-style preview while it “looks closely”

</td>
<td width="50%" valign="top">

**🌿 Identify**
- Streaming field notes (markdown journal)
- Powered by **Ollama** + `gemma3:latest`
- Runs locally — great when signal drops on the trail

</td>
</tr>
<tr>
<td width="50%" valign="top">

**📖 LogBook**
- Full-screen log from the top bar
- Thumbnails + snippets, **View full log** dialog
- Delete sightings when you need a fresh start

</td>
<td width="50%" valign="top">

**🎨 Experience**
- Autumn “trailside journal” UI
- Sticky header with GitHub link
- Save jumps you straight into LogBook

</td>
</tr>
</table>

> **Offline-friendly:** Once Ollama is running on your machine, identification doesn’t depend on a cloud API key.

---

## 🧰 What you'll need

| | Tool | Why |
|:---:|:---|:---|
| 🐍 | **Python 3.10+** | Runs the Streamlit app |
| 🤖 | **[Ollama](https://ollama.com/)** | Local vision + chat (`ollama serve`, model pulled) |
| 🐘 | **PostgreSQL** | Persists your LogBook (`fieldNotes` table) |

---

## 🚀 Quick start

<details open>
<summary><strong>Step 1 — Clone & install</strong></summary>
<br/>

```bash
git clone https://github.com/Gavinduachintha/Lookout.git
cd Lookout

python -m venv .venv
```

**Activate the venv**

| OS | Command |
|:---|:---|
| Windows | `.venv\Scripts\activate` |
| macOS / Linux | `source .venv/bin/activate` |

```bash
pip install -r requirements.txt
```

</details>

<details open>
<summary><strong>Step 2 — Ollama & model</strong></summary>
<br/>

Install from [ollama.com](https://ollama.com/), then:

```bash
ollama pull gemma3:latest
```

Keep Ollama running (desktop app or `ollama serve`).

</details>

<details open>
<summary><strong>Step 3 — PostgreSQL</strong></summary>
<br/>

Create a database (any name works for local dev). The app **auto-creates** the `fieldNotes` table on first run.

| Variable | Default | Description |
|:---------|:--------|:------------|
| `DB_HOST` | `localhost` | Database host |
| `DB_PORT` | `5432` | Port |
| `DB_NAME` | `postgres` | Database name |
| `DB_USER` | `postgres` | Username |
| `DB_PASSWORD` | — | **Required** |

**Windows (PowerShell)**

```powershell
$env:DB_PASSWORD = "your_password"
```

**macOS / Linux**

```bash
export DB_PASSWORD=your_password
```

</details>

<details open>
<summary><strong>Step 4 — Launch Trailside</strong></summary>
<br/>

```bash
streamlit run app.py
```

Your browser opens the app → **Identify** → **Save to LogBook** → you land in LogBook. Use **LogBook** / **Home** in the header anytime.

</details>

---

## 📁 Project layout

```text
Lookout/
├── 🍂 app.py              # Streamlit UI · Ollama · LogBook screens
├── 📝 prompts.py          # Naturalist system prompt
├── config/
│   └── 🐘 db.py           # PostgreSQL schema & CRUD
├── requirements.txt
└── README.md
```



## 🎨 UI palette

*Same autumn paper & forest tones as the app.*

| Swatch | Role | Hex |
|:------:|:-----|:----|
| 🟤 | Bark (body text) | `#5a4636` |
| 🌲 | Forest (headings) | `#1f3d2b` |
| 🍊 | Pumpkin (accents) | `#e8731a` |
| 📜 | Paper (background) | `#f6efe0` |

---

## ⚠️ Safety note

> AI vision can misidentify species — especially from one blurry photo.
>
> **Trailside is a learning companion, not a field certification tool.**  
> Verify anything important with a trusted local guide or reference.  
> **Never** eat or handle wild organisms you can’t identify with confidence.

---



---

## 🔧 Troubleshooting

<details>
<summary><strong>Click to expand common fixes</strong></summary>
<br/>

| Problem | Try this |
|:--------|:---------|
| `Database connection failed` | PostgreSQL running? `DB_*` env vars set? |
| `Model gemma3:latest not installed` | `ollama pull gemma3:latest` |
| `Can't reach Ollama` | Start Ollama or run `ollama serve` |
| LogBook empty after save | Check DB credentials; watch for save errors in the UI |

</details>

---

## 👋 Author

<div align="center">

**[@Gavinduachintha](https://github.com/Gavinduachintha)**

[Trailside on GitHub](https://github.com/Gavinduachintha/Trailside)

<br/>

*Built with care for hikers, curious beginners, and Hacktoberfest tinkerers.*

**Happy trails.** 🥾🍂

</div>
