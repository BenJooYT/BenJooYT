# Hi, I'm BenJooYT ⛏️

Minecraft developer building server-side gameplay systems, client mods, and tooling around the game. Most of my work is stuff I actually run and play with — dungeon generators, boss fights, automation, overlays.

> 🔒 marks a private repo — no public link, so the description below is all there is to see.

**Quick nav:** [Featured](#-featured-projects) · [Stack](#-technologies) · [Now](#-currently-working-on) · [Links](#-links)

---

## 🧾 About me

- I build **server gameplay** (Paper): procedural dungeons, combat stats, loot, bosses, parties, persistent progression.
- I build **client mods** (Forge, Fabric): automation on top of pathfinders, world scanning, inventory helpers.
- I build **tooling around the game**: external overlays, projection math, build pipelines.
- Currently on Android, developing with Termux + local repos and pushing when things compile.

---

## 🚀 Featured projects

| Project | What it is | Stack | Status |
|---|---|---|---|
| [**Dung**](https://github.com/BenJooYT/Dung) — room-based dungeon roguelite for Paper 1.21.x | Branching Isaac-style floors (random-walk gen, locked-until-cleared rooms, boss per floor), SkyBlock-style stats/loot, parties, persistent coins/upgrades. Two telegraphed bosses (Warden, Grovekeeper), rarity-scaled gear with mana-gated abilities. | Java 21 · Paper API · Gradle · JUnit | 🛠️ In development |
| **BaritoneExtras** 🔒 Private — client-side Forge companion mod for Baritone | Automation loops and task chains on top of Baritone's pathfinder: loop-mining, obtain-chains (loot → mine → craft → smelt), farm/replant, inventory helpers, plus a point-and-click GUI. Server only ever sees normal player packets. | Java 21 · Forge (1.21.x) · Baritone API | 🛠️ In development |
| [**external-mctool**](https://github.com/BenJooYT/external-mctool) — block scanner: Fabric mod + external overlay | Fabric client mod scans an 8-chunk radius for watched block IDs and streams matches + camera data as JSON over `127.0.0.1:25566`; a C# WinForms app draws a transparent click-through overlay. Personal singleplayer project. | Java (Fabric) · C# (.NET 8 WinForms) | 🧪 Working prototype |

<details>
<summary><b>Dung — what's inside</b></summary>

- Floor gen: branching room graph, BFS-farthest room = boss, shop/treasure/elite/secret placement; 800/800 connectivity harness green
- Combat: DMG/DEF/CRIT + mana recomputed SkyBlock-style from gear; rarity `COMMON → MYTHIC`; per-item Combat Power used for difficulty scaling
- Gear: `GearFactory` / `ItemPool` / `Affix` loot, 4 armor slots + weapons, sneak+right-click abilities (Rush, Cleave, Smash, Blade Storm, …)
- Multiplayer: `Party` / `PartyManager` runs, party-weighted difficulty
- Persistence: run gear lost on death, coins/kills/clears/class survive in `saves.yml`; shop, stash, workstation, upgrade UIs
- Presentation: sidebar HUD, boss bar, tab build view, clickable chat; WorldEdit-backed structure library

</details>

<details>
<summary><b>BaritoneExtras — what's inside</b></summary>

- Client-side only: `/bextra` commands (mine, get, farm, goto, …) + GUI screens, all tab-completed, no server mod needed
- Automation: `MiningLoop`, `ObtainTask` (chests → mine → craft with placed table → smelt with placed furnace), `FarmLoop` + replant, `VeinMiner`, `TunnelTask`, `SchematicBuilder`
- Helpers: auto-tool/armor, totem swap, chest sorting, trash filter, waypoints, survival handling via a shared `TaskQueue`
- Stack: Java, Forge + Baritone API, MIT-licensed, built via GitHub Actions

</details>

<details>
<summary><b>external-mctool — what's inside</b></summary>

- Mod: Fabric client mod for Minecraft 1.21.x, scans an 8-chunk radius (Y −64 to 64) every 10s for watched block IDs, streams matches + per-tick camera info as JSON
- Overlay: C# WinForms app with a config window (block list, FOV, mirror mode, persisted settings) plus a transparent, click-through, always-on-top overlay that draws outlines around matches
- Calibration: world-to-screen projection rebuilt per frame from camera yaw/pitch, works across resolutions and window modes

</details>

---

## 🛠️ Technologies

My working stack:

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=csharp&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![JUnit](https://img.shields.io/badge/JUnit-25A162?style=flat-square&logo=junit5&logoColor=white)

- **Languages:** Java · C# · a little Shell for build scripts
- **Minecraft:** Paper 1.21.x plugins · Fabric + Forge client mods · Baritone API · WorldEdit structures
- **Tooling:** WinForms overlays + world-to-screen projection math · GitHub Actions builds · JUnit gameplay harnesses

---

## 🔨 Currently working on

- **BaritoneExtras** 🔒 (private) — client-side Baritone automation mod
- **Dung** — dungeon content: difficulty tuning, room generation, boss encounters

---

## 🔗 Links

- GitHub: **[@BenJooYT](https://github.com/BenJooYT)**
- Pinned starting points: [Dung](https://github.com/BenJooYT/Dung) · [external-mctool](https://github.com/BenJooYT/external-mctool)

_Just GitHub — no email, site, or socials listed._
