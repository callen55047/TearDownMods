# Concept: Orbital station (military transport / deployable facility)

## Elevator pitch

A **Teardown** **co-op / multiplayer** level on a **large, advanced military spaceframe**: part **long-endurance transport**, part **station that can deploy and anchor around a planet** (Earth or elsewhere). Interiors are **immersive and futuristic**—spacious habitable volumes, clear circulation, ops and engineering decks that feel **livable** and **purpose-built**, not cramped maintenance tunnels. **Artificial gravity** (or equivalent) inside contrasts with **vacuum EVA** outside the hull, where the player is **weightless** and needs a **space suit** and **oxygen**. Pacing can still borrow from **Black Ops Zombies**–style space maps for **layered unlocks** and environmental story, but the **spatial read** is wide, readable, and high-tech rather than claustrophobic.

## Setting flexibility

- **Orbit** — Earth, a fictional world, or a gas giant’s moon; skybox and story beats can match.
- **Role** — Military logistics / deployment platform: troop and equipment staging, command, docking for shuttles or drops, optional surface-link narrative if it “lands” or tethers as a forward base.

## Core fantasy

| In-station (pressurized) | Outside (vacuum) |
|--------------------------|------------------|
| Normal or “artificial gravity” walk/run | **Zero-G** (or low-G) free float |
| No suit required | **Space suit required** |
| Combat and exploration in **open, legible** bays, hab rings, command | Tethering, limited O₂, different weapons/feel |
| Hab, mess, training, labs, power, docking — **livable + military** | Hull, trusses, antennas, solar, debris, secrets |

**Failure mode:** If a player enters vacuum **without** a functioning suit (or runs out of oxygen), that character **dies** — clear rules (timer, trigger volume, or scripted damage). Rules should read consistently in **multiplayer** (per-player suit/O₂ state).

## Gameplay pillars

1. **Co-op first** — Objectives, airlocks, and EVA beats support **multiple players** (simultaneous exterior work, interior hold-the-line, splitting for parallel tasks). Scale encounter density or puzzle complexity with player count if the engine allows.
2. **Dual locomotion** — Interior: familiar Teardown movement in **generous** spaces. Exterior: float, push off surfaces, optional brief thruster tool.
3. **Risk/reward EVA** — High-value routes, objectives, or story outside; suit and O₂ gate duration and range; **buddy tether** or rescue beats optional.
4. **Progressive unlocks** — Bring sections online, open docking collars or deployment gates, restore airlocks or external access — **map expansion** without requiring round-based horde mode unless desired (horde modes can still be co-op).
5. **Secrets** — Logs, optional modules, visual detail, shortcuts in both gravity and zero-G; rewards that **teams** can discover together.

## Oxygen system — suits, depletion, refill, tethers

Each **player** has their own **space suit** when operating in vacuum. The suit carries a **finite oxygen supply** that **drains continuously** while exposed (rate can be flat or modified—see below). Running out means **death** or **incapacitation**, same as unsuited vacuum exposure, so the loop is always: **manage tank → find refill or tether → complete objective → return or extend**.

### Baseline rules (per player)

- **Tank** — One primary capacity (time or abstract units). Optionally a **reserve** slot (spare bottle) unlocked by progression or pickup.
- **Drain** — Steady passive use. Interesting knobs: **higher drain while sprinting / using EVA thrusters**, **temporary spike after taking suit damage**, **lower drain** when stationary on a handhold (encourages pausing to plan).
- **Replenish without tether** — **Interior refill stations** (locker rooms, airlock consoles, med-bay scrubbers), **portable O₂ canisters** (consumable pickup), or **brief dock** at an airlock interface that tops you up before you push off again. Co-op: one player can hold a position at a console while others cycle through refills during a fight.

### Tethering (umbilical)

Players can attach an **umbilical cable** from their suit to a **station anchor** (airlock frame, external utility port, truss jack, deployable reel dropped by a teammate inside).

- **Effect (pick a clarity-friendly default)**  
  - **Sustain mode** — While connected and within range, O₂ stays at **maximum** (station supplies gas; tank logic is “capped full”). Best for **long EVA repair** and **low-friction co-op** teaching.  
  - **Refill mode** — Tether **accelerates refill** toward max but does not instantly freeze drain unless implemented as “net positive flow.” Good if you want **station power** or **flow capacity** to matter.  
  - **Hybrid** — Sustain only up to a **throughput cap**; heavy exertion can still net drain until the player slows down.

- **Range** — **Maximum cable length** defines how far you can go; exceeding it **yanks**, **disconnects**, or **damages** the connector (design choice). In zero-G, range is a **sphere** from the anchor, not floor distance—great for **vertical** exterior geometry.

- **Anchors** — Not every hull face has a port; **sparse anchors** create routing puzzles. **Mobile anchor**: another player carries a reel, or a **slow-moving drone** spool, extending team reach.

### Gameplay ideas the system enables

| Idea | What players do |
|------|------------------|
| **Untethered sprint vs. umbilical crawl** | Risk a **timed** crossing to grab an objective vs. **safe** tethered work that limits angle and speed. |
| **Cable routing** | Route the umbilical **around** solar wings or antennae so it does not **snag** on geometry or future destruction (Teardown: broken panels might **sever** or trap lines). |
| **Power / logistics coupling** | If station **power** or **life-support** is degraded, **refill speed drops**, tether **sustain** flickers, or **fewer anchors** are online—ties EVA tension to **interior objectives**. |
| **Anchor hunt** | An objective requires EVA but the **nearest port is offline**; team must **restore** a panel or **carry** a portable anchor from an airlock. |
| **Relay EVA** | Player A tethers from the airlock; Player B connects a **second line** from A’s reel or a mid-truss jack so B can reach a **far** antenna—**chain length** limited by ports and cable inventory. |
| **Buddy rescue** | Downed or panicked player **low O₂**; teammate **shares** a short emergency hose (timed interaction) or **drags** them to an airlock—explicit **co-op save** beat. |
| **Tether as vulnerability** | Enemies or hazards **target the line** (or it gets caught in fire/debris); **disconnect** drops you to tank-only countdown. |
| **No-anchor zones** | Certain debris fields or **hot** hull sections have **no** ports; must go **bottle-only** or install a **temporary stake** as a one-way mission step. |
| **Suit upgrades** — Progression | **Longer cable**, **larger tank**, **efficient scrubber** (slower drain), **quick-connect** (faster attach under pressure). |

### Co-op–specific beats

- **Staggered refills** — Limited concurrent refill slots at one console; queueing creates **cover** assignments.
- **One tether, two jobs** — One anchored player **holds** a winch while another uses **slack** to swing to a hatch (communication / timing).
- **O₂ budgeting** — Optional **hard mode**: station has a **shared liquid O₂ reserve**; tether sustain **drains the station** until a tanker objective is done—forces **prioritization** of who EVAs when.

### Presentation (player readability)

- **Visor / UI** — Tank percentage, time-to-empty at current drain, **tether tension** or **range ring** when near limit.
- **Audio** — Breathing stress as O₂ drops; **clean hiss** when tether flow is good; **alarm** when disconnected or line overstressed.

### Implementation notes (high level)

- Per-player state: `suit_equipped`, `o2_current`, `tether_anchor_id | nil`, `drain_multiplier`.
- Tether validation: distance from anchor ≤ `cable_length`, line-of-sight optional (some games allow “soft” LOS for fun; hard LOS is more punitive).
- Refill volumes: triggers at consoles, airlock thresholds, or interaction with pickups.

## New or custom content (conceptual)

### Equipment and systems

- **Space suit** — Per-player vacuum shell; optional visor HUD, muffled comms, low-O₂ vignette or audio.
- **Oxygen** — Depleting tank, interior / pickup refill, **umbilical tether** to anchors with range and sustain-or-refill behavior; see **Oxygen system** section above.
- **Airlocks** — Clear transition volumes: suit check, pressure cues, optional streaming split for exterior.

### Weapons and tools

- **Interior weapons** — Military-sci-fi arsenal matching a deployment platform.
- **Exterior / EVA tools** — Recoil maneuvering, tether gun, hull/cutting tools (Teardown-friendly destruction), low-impulse weapons suited to zero-G.

### Technical directions (implementation notes)

- **Gravity zones** — Volumes or tags: interior gravity vs. exterior zero/custom G; document API-specific approach.
- **Vacuum damage** — When `in_vacuum && !suit_equipped` or O₂ depleted.
- **Level design** — Favor **volume and silhouette**: hab rings, multi-deck cores, visible truss or spine, large windows or observation; exteriors readable against **planet or starfield**. Avoid relying on **narrow corridor** combat as the default identity. Interiors should allow **multiple players** to maneuver and read each other’s actions.

## References (tone and structure)

- **Black Ops Zombies** space maps — optional reference for **unlock flow** and mystery, not for tight maze density.
- **Deployable / transport sci-fi** — carriers, O’Neill-adjacent hab logic, military staging bays (Halo, The Expanse, NASA concept art) for **scale and livability**.
- **Real station grammar** — Docking ports, solar/truss, airlock etiquette (readability, not ISS-claustrophobia as the goal).

## Open questions

- Target **player count** (2–4, or higher) and how Teardown sessions handle it for this mod?
- Single large map vs. streamed interior/exterior layers?
- Fixed orbit (Earth) vs. abstract “any world” skybox?
- Enemy placement: interior-only vs. drones / EVA threats outside; **co-op** spacing and aggro?
- O₂ tether: **sustain-at-max** vs **refill-over-time** vs hybrid—what reads best in Teardown’s UI and session length?
- **Physical cable** (snag, wrap, destruction) vs **abstract tether range** from anchor only?
- Should **station reserves** be infinite for tether, or a **shared budget** for hard tension?
- Emergency **player-to-player** O₂ transfer: in scope for v1 or later?

## Status

**Concept only** — No implementation commitment until scoped in `mods/` with a target Teardown version and API checklist.
