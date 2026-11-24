<div align="center">

# TenteCreate

**A clean, powerful all-in-one hub for Roblox, with smart automation, persistent config, and a polished ESP.**

![Version](https://img.shields.io/badge/version-1.9.8-9F73FF?style=for-the-badge)
![Platform](https://img.shields.io/badge/platform-Roblox-00C8FF?style=for-the-badge)
![Interface](https://img.shields.io/badge/interface-xsx%20Lib-50FF8C?style=for-the-badge)
![Status](https://img.shields.io/badge/status-active-FF69B4?style=for-the-badge)

<br>

<img src="Menu%20-%20image.jpg" alt="TenteCreate - Main tab" width="760">

<sub>The Main tab: combat, automation and extras in one place.</sub>

</div>

---

## Table of Contents

- [Overview](#overview)
- [What's New in v1.9.8](#whats-new-in-v198)
- [Features at a Glance](#features-at-a-glance)
- [Main Tab](#main-tab)
  - [Combat](#combat)
  - [Automation](#automation)
  - [Extras](#extras)
- [ESP Tab](#esp-tab)
- [About Tab and Interface](#about-tab-and-interface)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
- [Tips and Notes](#tips-and-notes)
- [Changelog (highlights)](#changelog-highlights)
- [Disclaimer](#disclaimer)
- [Credits](#credits)

---

## Overview

**TenteCreate** brings the actions you repeat the most into a single, compact menu. Turn a feature on, and it quietly takes care of the rest: slapping at the right moment, dodging, answering the suspects prompt, hiding ads and purchase prompts, joining open arenas, recovering from bad teleports, and showing you where every player is.

It was built around four ideas:

- **Simple.** Every feature is a single switch. Everything that can be tuned (strength, delay, colors) sits right under it.
- **Smart.** Features react to what is actually happening in the game instead of firing blindly.
- **Persistent.** Your toggles, strength, delay and ESP colors are saved and restored the next time you run the script.
- **Clean.** A small, draggable window with notifications, a live FPS counter and one-click minimize and close.

---

## What's New in v1.9.8

| Area | What changed |
| :-- | :-- |
| **Config save** | Toggles, strength, delay and ESP settings are saved automatically and restored on the next run |
| **Slap strength** | Minimum strength is now **0.01** (1%). Custom accepts **0.01 – 1** |
| **Slap Max** | On each `SlapQueue`, waits the **same Slap Delay** as Auto Slap, then fires **one** `SendSlap(1)` — never two or three |
| **Auto Slap ↔ Slap Max** | Cannot run together. Turning one on turns the other off |
| **Auto game** | Smarter arena pick, hop to fuller lobbies, waiting room when all arenas are busy, no join into full/in-progress matches |
| **AntiBug** | Internal Auto Game protection against random/bugged coordinates (not flying). Soft reset, then hard restart if it keeps happening |
| **No Gamepass Ad** | Closes only the Roblox purchase prompt, without breaking the game’s own GUIs |
| **GUI load** | Features start **only once**, after the real menu is ready (not during the loading screen) |
| **Re-execute** | Running the script again fully replaces the previous TenteCreate instance and keeps your saved settings |

---

## Features at a Glance

| Feature | What it does |
| :-- | :-- |
| **Auto Slap (HIT KILL)** | Queues and lands slaps when the slap button appears, with your strength and delay |
| **Slap Strength** | Max, Medium, Min (0.01), or custom **0.01 – 1** |
| **Slap Delay** | **0 – 3 s** between queue and hit (shared by Auto Slap and Slap Max) |
| **Auto Dodge** | Keeps dodging while enabled |
| **Auto Suspects** | Picks the closest player and submits the guess when the panel opens |
| **Slap Max (no auto)** | On each manual `SlapQueue`, waits your Slap Delay, then fires **one** full-strength `SendSlap(1)` |
| **Don't watch the ad** | Keeps the streak-save ad prompt hidden |
| **No Gamepass Ad** | Blocks the native Roblox purchase prompt only |
| **Auto game** | Joins open arenas, hops when another lobby has more players, waits when everything is full |
| **AntiBug** | Soft-resets Auto Game on bugged teleports; hard-restarts if it keeps triggering |
| **ESP** | Chams, boxes, names, distance, health bars and tracers, fully recolorable |
| **Config** | Auto-saves and restores your setup |

---

## Main Tab

### Combat

#### Auto Slap (HIT KILL)

When the game shows the slap button, TenteCreate queues the slap, waits your **Slap Delay**, and lands the hit with your chosen strength.

- Works only after the menu is fully loaded.
- Stops as soon as you turn it off.
- **Cannot** run at the same time as **Slap Max**.

#### Slap Strength

| Option | Strength |
| :-- | :--: |
| Max | 1 |
| Medium | 0.5 |
| Min | **0.01** |
| Custom | any value from **0.01** to **1** |

For **Custom**, type the value and select *Custom* in the list. Dots and commas both work as decimals; out-of-range values are clamped.

#### Slap Delay

Time between queueing and landing the slap: **0 – 3 seconds**.  
**0** = no wait. This same value is used by **Slap Max**.

---

### Automation

#### Auto Dodge

Dodges continuously while enabled.

#### Auto Suspects

When the suspects panel opens, submits the **closest** player’s username once per appearance.

---

### Extras

#### Don't watch the ad

Hides the streak-save ad and keeps it hidden if the game tries to show it again.

#### No Gamepass Ad

Intercepts only the **Roblox purchase prompt** (gamepass / product). Your in-game shop UI is left alone.

#### Auto game

Hands-free matchmaking with clearer rules:

| Arena label | Meaning | Action |
| :-- | :-- | :-- |
| Has `/` (e.g. `2/5`) and not full, countdown ≥ 3 | Open lobby | Can join |
| Only numbers (no `/`) | Match in progress | Do not join |
| Full / countdown 0–2 | Closing or full | Skip |

**Lobby hop (only while waiting, never mid-match):**

| Your arena | Other arena | Action |
| :-- | :-- | :-- |
| 1 (only you) | 1+ | Teleport to the fuller/other lobby |
| 2 | 2 | Stay |
| 2 | 0 | Stay |

**Waiting room:** if every arena is in a match (numbers only), you are moved to a hold position with a short “A moment of waiting” UI until a lobby opens again.

Notifications stay limited to: entered arena, left arena, entered another arena (with player count when available).

#### AntiBug (built into Auto Game)

Not a button — always active while Auto Game is on.

- Detects **bugged / random teleports** (not normal flying).
- Temporarily pauses Auto Game code, waits **0.1 s**, then resumes.
- Shows a red notification when it runs.
- If it triggers many times in a short window, it performs a **hard restart** of the Auto Game systems.

#### Slap Max (no auto)

You slap manually. TenteCreate only finishes the hit:

1. Detects `SlapQueue:FireServer()`
2. Waits the **same Slap Delay** as Auto Slap
3. Fires **exactly one** `SendSlap(1)`

No bar watching, no double/triple hits. **Cannot** run together with Auto Slap.

---

## ESP Tab

<div align="center">

<img src="Esp%20-%20image.jpg" alt="TenteCreate - ESP tab" width="760">

<sub>The ESP tab: pick what you want to see and how it looks.</sub>

</div>

<br>

| Element | Description |
| :-- | :-- |
| **Chams** | Outline and soft fill through walls |
| **Boxes** | Rounded box around each player |
| **Names** | Display name above the player |
| **Distance** | Distance under the player |
| **Health Bar** | Bar beside the box (green → red) |
| **Tracers** | Line from the bottom of the screen to each player |

**Settings**

- **Max Distance** — hide players beyond this range  
- **Fill Transparency** — how solid the chams fill is  

**Colors** (outline / fill / text)

- Presets: Purple, Cyan, Red, Green, Yellow, Orange, Pink, White, **Rainbow**
- Custom: `#RRGGBB` or `R,G,B`

ESP settings are included in the saved config.

---

## About Tab and Interface

<div align="center">

<img src="About%20-%20image.jpg" alt="TenteCreate - About tab" width="760">

<sub>The About tab: version, credits and menu shortcut.</sub>

</div>

<br>

- **Compact window** with scroll on every tab  
- **Draggable** title area  
- **Minimize / close** in the header  
- **Right Alt** — hide / show the menu  
- **Notifications** for toggles and important Auto Game events  
- **Watermark** — version, username, FPS  
- **Credit badge** with creator avatar  

Closing the hub unloads features, ESP, waiting room and connections cleanly. Running the script again replaces the previous TenteCreate instance only (other scripts are left alone).

---

## How It Works

**Same language as the game.**  
Actions use the game’s own remotes (`SlapQueue`, `SendSlap`, `Dodge`, `Guess`, `Exit`, …), so the server sees the same kind of messages as normal UI buttons.

**Watches the UI.**  
Slap button, suspects panel, Exit, arena boards — tracked continuously. If the element isn’t there, nothing fires.

**Once per appearance (where it matters).**  
Auto Slap / Slap Max / Suspects avoid pointless spam. Slap Max especially: **one queue → one delayed max hit**.

**Reads the world.**  
Nearest player for suspects, arena labels for matchmaking, positions/health for ESP.

**Starts only when the menu is ready.**  
Loading / intro does not arm Auto Game or combat. Systems start once after the real GUI is open, so nothing runs twice on inject.

**Config file.**  
`TenteCreate_Config.json` stores state and settings when the executor supports `writefile` / `readfile`.

---

## Getting Started

1. Open Roblox and join the supported game.  
2. Run **TenteCreate** with a compatible executor.  
3. Wait for the intro and the **TenteCreate loaded!** notification.  
4. Open **Main** and enable what you need.  
5. Open **ESP** to customize visuals.  
6. Press **Right Alt** anytime to hide or show the menu.

Your last setup is restored automatically when a config file is present.

---

## Tips and Notes

<details>
<summary><b>The menu disappeared. Where did it go?</b></summary>

<br>

Press **Right Alt**. If you minimized it, click **+** in the header.

</details>

<details>
<summary><b>Auto game isn’t joining.</b></summary>

<br>

It only joins lobbies with `/` in the label, not full, and with countdown at least **3**. If every arena shows only numbers, the waiting room appears until one opens.

</details>

<details>
<summary><b>Slap Max doesn’t fire.</b></summary>

<br>

Enable **Slap Max** with **Auto Slap off**. Play normally so the game fires `SlapQueue`. After your **Slap Delay**, one `SendSlap(1)` is sent. Set delay to `0` for an immediate max hit.

</details>

<details>
<summary><b>Can Auto Slap and Slap Max run together?</b></summary>

<br>

**No.** Enabling one disables the other on purpose so hit-kill behavior stays consistent.

</details>

<details>
<summary><b>AntiBug keeps notifying me.</b></summary>

<br>

That means the client is being moved to unexpected coordinates while Auto Game is on. AntiBug soft-resets; if it happens often, it hard-restarts Auto Game. If it still fails, re-execute the script once.

</details>

<details>
<summary><b>How many chams at once?</b></summary>

<br>

Roblox limits simultaneous Highlights (chams) to about **31**. Boxes, names, distance, health and tracers are not limited the same way.

</details>

---

## Changelog (highlights)

### v1.9.8
- Slap Max: same delay as Auto Slap, **one** `SendSlap(1)` per `SlapQueue`
- Auto Slap and Slap Max mutually exclusive
- Min strength **0.01**; custom range **0.01 – 1**
- Auto game: join rules, lobby hop, waiting room, no mid-match switches
- AntiBug system for Auto Game
- No Gamepass Ad limited to native purchase prompts
- Config persistence
- Features arm only after the menu is ready
- Clean re-inject of TenteCreate only

### Earlier
- ESP (chams, boxes, names, distance, health, tracers, colors)
- Auto Dodge, Auto Suspects, Don’t watch the ad
- Compact UI with minimize, drag, Right Alt, watermark and notifications

---

## Disclaimer

TenteCreate is provided as-is, for educational and personal use. Using scripts in online games may go against the rules of the game or of Roblox and can lead to penalties on your account. **Use it at your own risk.** The author is not responsible for any consequences.

---

## Credits

- **Created by [ByteBandit_ofici](#)**
- **Interface:** built with the **xsx Lib** UI library, created by **bungie**.

<div align="center">

<br>

**If you enjoy TenteCreate, share it with your friends.**

<sub>Made with care by ByteBandit_ofici · v1.9.8</sub>

</div>
