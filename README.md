# Wipeout

**A vibrant, chaotic river-race card game for the eTwinning project *Guardians of our Waters*.**

**[▶ Play live](https://physicsplay.github.io/Wipeout-game/)** — works in any modern browser, on any device. No installation, no accounts, no downloads.

---

## What it is

Two to six crews race down a virtual river from Alpine Source to Delta. Each round, every crew secretly picks one card. Cards reveal simultaneously. Paddle forward, sprint for glory, sabotage rivals, shield yourself, or scoop river garbage for bonus points.

Between those decisions, a water-science quiz question appears — answer correctly for a bonus token. Hazard tiles punish careless positioning. First crew to reach the Delta (tile 30) triggers the final scoring — or after 10 rounds, whoever got furthest wins.

Fast, funny, strategic, and surprisingly educational. Built for ages 14–19, playing time ~15 minutes, designed for classroom energy.

---

## How to play

### Setup

1. One crew opens the live link and clicks **Create a room** → enters a crew name → picks a country.
2. Other crews join using the 4-letter room code (or by scanning the QR code). Each crew joins from its own device.
3. Once at least 2 crews are in the lobby, any crew can press **Start race**.

### Each round

Every crew picks one card from their hand of six:

| Card | Effect |
|---|---|
| 🚣 **PADDLE** | +2 tiles · reliable · no cooldown |
| 💨 **SPRINT** | +3 tiles, but vulnerable — sabotage hits harder · 1-round cooldown |
| 🗑️ **SCOOP** | 0 tiles, but +2 cleanup tokens (worth points at the end) |
| 🛡️ **SHIELD** | +1 tile AND blocks any sabotage this round · 1-round cooldown |
| 💥 **SABOTAGE** | Target crew moves -3 tiles · blocked by their shield · 3 uses per game |
| ⚓ **BRAKE** | 0 tiles, but immune to sabotage for 2 rounds · 2-round cooldown |

After choosing a card, also answer the round's **water-science quiz question** (+1 token if correct). All crews can answer.

When everyone locks in their card (or the 60-second timer runs out), cards reveal simultaneously. Resolution order: shields activate → sabotages apply → movement happens → hazards on landed tiles trigger → tokens update.

### The river

30 tiles divided into 5 themed segments:

- **Alpine Source** (1-6) — calm, cold, safe
- **The Rapids** (7-12) — fast water, hazards start appearing
- **Industrial Zone** (13-18) — oil slicks and debris fields; high risk, high reward
- **The Reeds** (19-24) — slow tangles, wildlife, sudden reeds
- **The Delta** (25-30) — the finish line

Specific tiles have hazards: whirlpools (random ±2 tiles), oil slicks (-1 token), debris fields (+2 tokens), plastic patches (slow you next round), sandbars (-1 tile). Some tiles help, some hurt — positioning matters.

### Round events

Each round draws a random event that shifts the rules: Chemical Spill, Algal Bloom, Sudden Downpour (+1 to all movement), River Patrol (sabotage costs tokens), Community Day (scoops pay double), Morning Fog (sabotage targets randomized), etc.

### Scoring

- **2 points per tile** reached
- **1 point per cleanup token**
- **+10 point bonus** for reaching the Delta

Game ends when any crew reaches tile 30, or after 10 rounds. Highest total points wins.

### Design principles

- **Simple rules, strategic depth.** Every card has a clear trade-off.
- **Fully objective scoring.** No teacher judgment, no voting, no style points.
- **Embedded education.** Water-science facts appear naturally through quizzes and flavor.
- **Chaos with fairness.** Limited sabotages, shared hazards, transparent rules.

---

## For teachers who want to run it in their classroom

The live link works out of the box. Crews just need internet and a modern browser.

### To fork this and run your own Firebase backend

1. **Fork this repository** (top right → Fork).
2. **Create a Firebase project** at [console.firebase.google.com](https://console.firebase.google.com).
3. **Enable Anonymous Authentication** (Authentication → Sign-in method → Anonymous → Enable).
4. **Create a Realtime Database** (Build → Realtime Database → Create database, region `europe-west1` recommended).
5. **Set security rules** to:
   ```json
   {
     "rules": {
       "wipeout_rooms": {
         "$roomId": {
           ".read": "auth != null",
           ".write": "auth != null"
         }
       }
     }
   }
   ```
6. **Add your GitHub Pages domain** to Authentication → Settings → Authorized domains.
7. **Copy your Firebase Web App config** and paste it into the `FIREBASE_CONFIG` object near the top of the `<script type="module">` block in `index.html`.
8. **Enable GitHub Pages** (Settings → Pages → Deploy from `main` branch, `/` root).

---

## Sister game

This is the companion piece to **[Confluence](https://physicsplay.github.io/Confluence-game/)** — the same project's slower, strategic, data-intelligence game. Wipeout is the vibrant race. Confluence is the cross-border investigation. Use whichever fits the mood of the class.

---

## Project context

Wipeout was built for the eTwinning project **Guardians of our Waters**, which connects secondary schools across six European countries (Italy, Spain, Greece, France, Slovakia, Bulgaria) to monitor local water quality and share findings.

The six project goals are embedded in the mechanics:

1. **Scientific inquiry & data literacy** — water-science quizzes in every round.
2. **International collaboration** — cross-border play is the baseline, not a theme.
3. **Environmental advocacy** — river cleanups (scoops) are a core scoring mechanic.
4. **Curriculum integration** — science, digital literacy, and strategic thinking in 15 minutes.
5. **Geospatial thinking** — river segments mirror real watershed structure.
6. **European citizenship** — cooperation and healthy competition between six countries.

---

## License

Released under the **MIT License** — see [`LICENSE`](./LICENSE).

Fork, modify, translate, adapt. If you build something interesting, a note back would be appreciated but is not required.

---

## Credits

Designed and built as part of the eTwinning project *Guardians of our Waters* (2025–26). Game design, code, and visual direction developed in collaboration with Anthropic's Claude.
