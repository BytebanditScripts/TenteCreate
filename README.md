<div align="center">

# TenteCreate

**A clean, powerful all-in-one hub for Roblox, with smart automation and a polished ESP.**

![Version](https://img.shields.io/badge/version-1.0-9F73FF?style=for-the-badge)
![Platform](https://img.shields.io/badge/platform-Roblox-00C8FF?style=for-the-badge)
![Interface](https://img.shields.io/badge/interface-xsx%20Lib-50FF8C?style=for-the-badge)
![Status](https://img.shields.io/badge/status-active-FF69B4?style=for-the-badge)

<br>

<img src="https://lh3.googleusercontent.com/pw/AP1GczNIjLKUaaUK-Vo_JmpkQCy6yPGrhdG6jmyd9wG9akkZikAtmluAmK900Yu46J9Qd_OwjNiL7TVblaqsuRnbMr7jCApAd03igIK4Zt3njuguoMtkt5RmrBsu1LjQPt6eI_3UqL29nJrxSponsjPmmhpl=w985-h663-s-no-gm?authuser=0" alt="TenteCreate - Main tab" width="760">

<sub>The Main tab: every automation one click away.</sub>

</div>

---

## Table of Contents

- [Overview](#overview)
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
- [Disclaimer](#disclaimer)
- [Credits](#credits)

---

## Overview

**TenteCreate** brings the actions you repeat the most into a single, compact menu. Turn a feature on, and it quietly takes care of the rest: slapping at the right moment, dodging, answering the suspects prompt, hiding annoying ads, joining open arenas and showing you where every player is.

It was built around three ideas:

- **Simple.** Every feature is a single switch. Everything that can be tuned (strength, delay, colors) sits right under it.
- **Smart.** Features react to what is actually happening in the game instead of firing blindly.
- **Clean.** A small, draggable window with notifications, a live FPS counter and one-click minimize and close.

---

## Features at a Glance

| Feature | What it does |
| :-- | :-- |
| **Auto Slap (HIT KILL)** | Slaps automatically every time the slap option appears, with your chosen strength and delay |
| **Slap Strength** | Max, Medium, Min, or a custom value from 0.1 to 1 |
| **Slap Delay** | From 0 to 3 seconds. Set it to 0 for no delay at all |
| **Auto Dodge** | Keeps dodging without you touching anything |
| **Auto Suspects** | Picks the closest player and submits them as your guess |
| **Slap Max (no auto)** | Fires a full-strength slap at the exact moment the timing bar reaches its mark |
| **Don't watch the ad** | Keeps the streak-save ad prompt out of your way |
| **Auto game** | Finds an open arena, joins it, and moves on to the next one when the match ends |
| **ESP** | Chams, boxes, names, distance, health bars and tracers, fully recolorable |

---

## Main Tab

### Combat

#### Auto Slap (HIT KILL)

When the game offers you a slap, TenteCreate takes it for you. It first queues the slap, waits for the delay you picked, and then lands the hit with your chosen strength.

- It reacts **once per appearance**, so it never spams.
- It stops the moment you switch it off, even if a slap is already waiting for its delay to finish.

#### Slap Strength

Choose how hard the slap is:

| Option | Strength |
| :-- | :--: |
| Max | 1 |
| Medium | 0.5 |
| Min | 0.1 |
| Custom | any value from 0.1 to 1 |

For **Custom**, type your value in the box and select *Custom* in the list. Values outside the allowed range are adjusted automatically, and both dots and commas work as decimal separators.

#### Slap Delay

The time between queueing the slap and landing it. Choose anything from **0 to 3 seconds**. A value of **0** removes the wait entirely.

---

### Automation

#### Auto Dodge

Dodges continuously while enabled. Switch it on before a round and focus on everything else.

#### Auto Suspects

When the suspects panel opens, TenteCreate checks who is **closest to you** and submits that player's full username as your guess, automatically. It answers once each time the panel appears.

---

### Extras

#### Don't watch the ad

Hides the streak-save ad prompt and **keeps it hidden**. If the game tries to show it again, it is dismissed right away.

#### Auto game

Hands-free matchmaking. TenteCreate reads the status board of every arena and decides for you:

| Arena status | Meaning | What TenteCreate does |
| :-- | :-- | :-- |
| Players out of capacity, with room left | Open and waiting for players | Joins it |
| Full capacity | Full | Skips it |
| Only numbers (no slash) | Match in progress | Stays where it is |
| The slash comes back | Match finished | Moves on to another open arena |

A few more details:

- If you die, it starts looking for a new arena as soon as you respawn.
- After a match ends, it prefers a **different** arena from the one you just left.
- If an arena stays in the waiting phase for too long, it looks for another one.
- If it can't find the arenas, you get a notification instead of silence.

#### Slap Max (no auto)

For the moments you want to do the slap yourself with perfect timing. When the timing bar shows up, TenteCreate watches it, and the instant it reaches its mark, a **full-strength hit kill** goes out. There is **no delay**, and it won't repeat until the next time the bar appears.

---

## ESP Tab

<div align="center">

<img src="https://lh3.googleusercontent.com/pw/AP1GczM4eOZ-l2O_OKtib_gGrqKWZbUbDdGDqdckaWHsT3vnnx3Zuf4ledku8CB5kRdZmZhz8lDH6fzLl8uH31OBrwf-Hp3gM81yB6zmUkLepeR7cHVpwtI_wzk5_w92hTBgzuWwtRBwfjpXhJILR5Z5gZqM=w913-h572-s-no-gm?authuser=0" alt="TenteCreate - ESP tab" width="760">

<sub>The ESP tab: pick what you want to see and how it looks.</sub>

</div>

<br>

See every player at a glance, through walls, with a presentation that stays easy on the eyes.

| Element | Description |
| :-- | :-- |
| **Chams** | A glowing outline and soft fill that wraps each player |
| **Boxes** | A rounded box around every player |
| **Names** | The player's name above them |
| **Distance** | How far away they are, shown under them |
| **Health Bar** | A slim bar beside the box that shifts from green to red as health drops |
| **Tracers** | A line from the bottom of your screen to each player |

**Settings**

- **Max Distance:** hide players beyond the range you choose.
- **Fill Transparency:** control how solid or see-through the chams fill is.

**Colors**

Outline/box, fill and text each have their own color, and you can set it two ways:

- **Presets:** Purple, Cyan, Red, Green, Yellow, Orange, Pink, White and **Rainbow** (a smooth animated color cycle).
- **Custom:** type any color as a hex code (for example `#9F73FF`) or as three numbers (for example `255, 0, 0`).

Players disappear from the ESP the moment they die or leave, and everything is removed cleanly when you turn it off.

---

## About Tab and Interface

<div align="center">

<img src="https://lh3.googleusercontent.com/pw/AP1GczP78egZXgWFGQsRwb3EpsUOVagoM3Y3EP6_BWKsvYsS3l2484JGP30Kg5673C9Eg1k7UsM-Ooupsh430rXlE4FjK6DO1suqA1bytHfE9_6R9zETtCbGNx6PI8cARtW6SwWl2UhCZp238j_3p9LSsf8x=w915-h607-s-no-gm?authuser=0" alt="TenteCreate - About tab" width="760">

<sub>The About tab: version, credits and menu shortcut.</sub>

</div>

<br>

The interface is designed to stay out of your way:

- **Compact window.** Smaller than a typical hub, and fully scrollable on every tab.
- **Draggable.** Move it anywhere on your screen.
- **Minimize and close.** Collapse the window to its title bar, or close it to shut everything down and remove every trace.
- **Hide and show.** Press **Right Alt** to toggle the menu at any time.
- **Notifications.** A short message confirms every switch you flip, and tells you when something needs attention.
- **Live watermark.** Shows the version, your name and your current FPS.
- **Credit badge.** A small badge in the header shows the creator along with a profile picture.

---

## How It Works

You don't need any technical background to use TenteCreate, but here is the idea behind it.

**It speaks the game's own language.**
The game has its own way of handling actions: when you press a button, your device tells the game's server what you did. TenteCreate sends those very same messages, so the game treats them just like the ones from its own buttons.

**It watches the screen, like you do.**
Most features wait for something to appear: a slap option, the suspects panel, the timing bar, an arena status board. TenteCreate keeps an eye on these elements many times per second and reacts the moment they change. If the thing it is waiting for isn't there, it does nothing.

**It acts once, then waits.**
To avoid spamming, a feature that reacts to something appearing fires **once per appearance**, then resets when that element goes away. That keeps everything natural and predictable.

**It reads the world around you.**
For nearest-player features, it measures real distances between characters. For the arena logic, it reads each arena's player count and uses it to tell whether a match is open, full, running or over. For the ESP, it follows every player's position and health in real time.

**It keeps your screen tidy.**
All visuals live in their own layer and are fully removed when you close the hub. Turning a feature off stops it immediately.

**Everything is optional.**
Every feature starts **off**. Turn on only what you need.

---

## Getting Started

1. Open Roblox and join your game.
2. Run **TenteCreate** with a compatible script executor.
3. Wait for the intro and the *TenteCreate loaded!* notification.
4. Open the **Main** tab and flip on what you want.
5. Visit the **ESP** tab to choose what you see and how it looks.
6. Press **Right Alt** whenever you want to hide or show the menu.

---

## Tips and Notes

<details>
<summary><b>The menu disappeared. Where did it go?</b></summary>

<br>

Press **Right Alt** to bring it back. If you minimized it, click the **+** button in the header.

</details>

<details>
<summary><b>Auto game isn't joining anything.</b></summary>

<br>

Make sure at least one arena has room for more players. Full arenas and arenas with a match in progress are skipped on purpose. If the arenas can't be found at all, TenteCreate lets you know with a notification.

</details>

<details>
<summary><b>Slap Max doesn't fire.</b></summary>

<br>

It only works while the timing bar is on screen, and it fires when the bar reaches its mark. Make sure the switch is on **before** the bar appears.

</details>

<details>
<summary><b>How many players can the ESP outline at once?</b></summary>

<br>

Roblox limits how many glowing outlines (chams) can be drawn at the same time, at around 31. Boxes, names, distance, health bars and tracers don't have that limit.

</details>

<details>
<summary><b>Can I use both Auto Slap and Slap Max?</b></summary>

<br>

Yes, they are independent. Auto Slap takes the slap for you with the strength and delay you chose, while Slap Max is for perfectly timed full-strength hits.

</details>

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

<sub>Made with care by ByteBandit_ofici</sub>

</div>
