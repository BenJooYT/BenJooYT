# Hi, I'm BenJooYT 👋

Java / Kotlin developer building Minecraft gameplay systems, Android games, and small AI tools. Most of my work is systems-heavy stuff I actually run and play with — dungeon generators, game loops, overlays, keyboards.

> No Roblox repos on this account (yet) — everything below is from public repos you can read and build today.

**Quick nav:** [Featured](#-featured-projects) · [Stack](#-technologies) · [Now](#-currently-working-on) · [Links](#-links)

---

## 🧾 About me

- I build **Minecraft plugins/mods** (Paper, Fabric) with real game systems: procedural floors, combat stats, loot, bosses.
- I build **Android apps/games** in Java and Kotlin — custom rendering, IME keyboards, on-device AI experiments.
- I like **technical toys**: projection math, Markov-chain music, LAN multiplayer, LLM tooling.
- Currently on Android, developing with Termux + local repos and pushing when things compile.

---

## 🚀 Featured projects

| Project | What it is | Stack | Status |
|---|---|---|---|
| [**Dung**](https://github.com/BenJooYT/Dung) — room-based dungeon roguelite for Paper 1.21.x | Branching Isaac-style floors (random-walk gen, locked-until-cleared rooms, boss per floor), SkyBlock-style stats/loot, parties, persistent coins/upgrades. Two telegraphed bosses (Warden, Grovekeeper), rarity-scaled gear with mana-gated abilities. | Java 21 · Paper API · Gradle · JUnit | 🛠️ In development — v1.5.1, last active Sep 2026 |
| [**BSnake**](https://github.com/BenJooYT/BSnake) — Snake with teeth for Android | Arcade mode (32×32 toroidal grid, 4 boss snakes, upgrade cards, 20 challenge objectives) + Classic pure-snake mode. Custom Canvas renderer/game loop, swipe input queue, Markov-chain menu music + synth SFX, Wi-Fi LAN multiplayer, in-app update checker. Zero dependencies. | Java · Android SDK (Canvas) · Gradle | ✅ Playable — v1.8.0 release |
| [**external-mctool**](https://github.com/BenJooYT/external-mctool) — block scanner: Fabric mod + external overlay | Fabric client mod scans an 8-chunk radius for watched block IDs and streams matches + camera data as JSON over `127.0.0.1:25566`; a C# WinForms app draws a transparent click-through overlay. Personal singleplayer project. | Java (Fabric) · C# (.NET 8 WinForms) | 🧪 Working prototype |
| [**android-ai-ime**](https://github.com/BenJooYT/android-ai-ime) — AI-powered Android keyboard | Compose IME with conversation memory, switchable providers (CheaperInference), Room persistence, Hilt DI, privacy onboarding. | Kotlin · Compose · Room · Hilt · Retrofit | 🧪 Early / experimental |

**Also tinkering:** [**open-jarvis**](https://github.com/BenJooYT/open-jarvis) — a fork of [`tokenarc/open-jarvis`](https://github.com/tokenarc/open-jarvis) (Android AI agent) where I've been fixing CI/build issues so the APK actually compiles. Not my original project, keeping it honest.

<details>
<summary><b>Dung — what's actually built (verified from the repo)</b></summary>

- Floor gen: branching room graph, BFS-farthest room = boss, shop/treasure/elite/secret placement; 800/800 connectivity harness green
- Combat: DMG/DEF/CRIT + mana recomputed SkyBlock-style from gear; rarity `COMMON → MYTHIC`; per-item Combat Power used for difficulty scaling
- Gear: `GearFactory` / `ItemPool` / `Affix` loot, 4 armor slots + weapons, sneak+right-click abilities (Rush, Cleave, Smash, Blade Storm, …)
- Multiplayer: `Party` / `PartyManager` runs, party-weighted difficulty
- Persistence: run gear lost on death, coins/kills/clears/class survive in `saves.yml`; shop, stash, workstation, upgrade UIs
- Presentation: sidebar HUD, boss bar, tab build view, clickable chat; WorldEdit-backed structure library

</details>

<details>
<summary><b>BSnake — what's actually built (verified from the repo)</b></summary>

- Modes: Arcade (bosses, progression, 3 cameras) + Classic (screen-filling board, static camera)
- Bosses: CHASER, WALL_BUILDER (wall-capture by closed loop), HEALER, MIRROR (control-flipping fruit); spawn gap scales 100 → 400; cinematic death sequence + upgrade-card draft
- Audio: procedural Markov-chain menu music (C major, 120 BPM), synthesized SFX, no audio thread stutter
- Multiplayer: host/client over LAN (`GameServer` / `GameClient` / hotspot helper), with thread-safety fixes in 1.7.7
- Meta: 20 arcade challenges (3 random per run), top-20 leaderboard, live color preview, dev mode, `version.json` update checker

</details>

---

## 🛠️ Technologies

Based on what's actually in my repos — not a wishlist.

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=csharp&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![JUnit](https://img.shields.io/badge/JUnit-25A162?style=flat-square&logo=junit5&logoColor=white)

- **Languages:** Java · Kotlin · C# · a little Shell for build scripts
- **Minecraft:** Paper 1.21.x plugins (Java 21) · Fabric client mods · WorldEdit structures
- **Android:** Canvas custom rendering + game loops · Compose UI · IME services · Room / DataStore / Hilt / Retrofit
- **Desktop/tooling:** .NET 8 WinForms overlays · world-to-screen projection math · GitHub Actions APK builds

_No Lua/Luau on this account right now — if a Roblox project lands here, it'll show up in Featured._

---

## 🔨 Currently working on

- **Dung** — combat-power difficulty tuning, room/corridor generation fixes, boss encounters (most recent pushes, Sep 2026)
- **Android games** — BSnake 1.8.x stability (multiplayer thread safety, boss balance)
- **Local AI tooling** — Android IME + on-device agent experiments, keeping forks building

---

## 🔗 Links

- GitHub: **[@BenJooYT](https://github.com/BenJooYT)**
- Pinned starting points: [Dung](https://github.com/BenJooYT/Dung) · [BSnake](https://github.com/BenJooYT/BSnake) · [external-mctool](https://github.com/BenJooYT/external-mctool) · [android-ai-ime](https://github.com/BenJooYT/android-ai-ime)

_No email, site, or socials listed here — if it's not linked from this profile or a repo, it's not mine to advertise._
