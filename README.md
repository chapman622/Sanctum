# Sanctum Cue Board (Alt1)

Big on-screen visual cues for all three Sanctum of Rebirth bosses — **Vermyx, Brood Mother**, **Kezalam, the Wanderer**, and **Nakatra, Devourer Eternal** — in both Normal and Hard Mode.

## What it does

- Large coloured banners appear over the game when a mechanic is called.
- Boss tabs (Vermyx / Kezalam / Nakatra) switch which mechanic set is being watched and tested — auto-read watches **all three at once** and switches the tab for you as you progress through the instance.
- A Normal/Hard Mode toggle adds a short "HM:" timing note under the banner for mechanics that behave differently in Hard Mode (it does not change what triggers the cue).
- Manual test buttons (and number keys 1–0) for instant cues, per boss.
- Auto mode watches the chatbox for the boss's actual spoken lines — **only for mechanics with a confirmed chat line**. Anything without a documented line is clearly marked "manual only" so you're not relying on a guess.

## Confirmed chat-triggered cues

| Boss | Cue | Chat line |
|---|---|---|
| Vermyx | Moonstone Shard | *Snaaaarl!* |
| Vermyx | Coilspawn | *Craaaaa!* |
| Vermyx | Soul Rush | *Rarghh!* |
| Vermyx | Soul Bomb | *Kreeee!* |
| Vermyx | Scarab Healer | *Heaall...* |
| Kezalam | Blast — Scattered | *Dhaaarken* |
| Kezalam | Blast — Close | *Graaah* |
| Kezalam | Blast — Mid | *Kyaaa* |
| Kezalam | Blast — Far | *Hrrrr* |
| Kezalam | Blast — Line | *Paiiin* |
| Nakatra | Soulfire Wave | "The soulfire erases all." |
| Nakatra | Phase 2 start | "The Sanctum is mine to control." |
| Nakatra | Hieroglyphs | "Face judgement foul wretch." / "Feel the power beneath your feet!" |
| Nakatra | Obliterate warning | "Prepare for death..." |
| Nakatra | Obliterate hit | "Be obliterated!" |
| Nakatra | Shockwave | "You cannot stop me!" |

Everything else (Wyrmfire, Moonstone Prison, Unstable Scarabs, Obelisk phase, Summon Scarabs, Nefthys phase, Shadowsands drag, Barrage) has no publicly documented chat line, so those fire from the test grid / your own keybinds only. If you notice the exact line for one of these while playing, open the debug log, copy it, and it can be added.

## Shared with the Zamorak board

This uses the exact same working internals as your Zamorak Cue Board — the `window.Chatbox` reader init, the `overLayImage(x, y, imgstr, imgwidth, time)` call signature, the `rnd()` int-rounding wrapper for every Alt1 overlay call, and the `clean()`/`matches()` whitespace-stripped substring matching. If you already have an `icons/` folder from the Zamorak app (freedom.png, anticipation.png, deflect_melee.png, debilitate.png, deflect_magic.png, devotion.png, resonance.png, reflect.png), copy it into this folder too — a few Sanctum cues (Soul Bomb, Moonstone Prison, Obliterate, Nefthys) reuse those same ability icons. If the folder isn't there, those cues just fall back to text-only, nothing breaks.

## How to install

1. Make sure Alt1 Toolkit is installed (<https://runeapps.org/alt1>).
2. Copy this whole `sanctum-cue-board` folder somewhere permanent (e.g. Documents), next to your Zamorak folder.
3. In Alt1:
   - Right-click the Alt1 icon → **Add app**
   - Point it at the `appconfig.json` file inside the folder
   - Or open the folder in the Alt1 browser and click "Add app"
4. Grant **Pixel** and **Overlay** permissions when prompted (right-click the app → Permissions).

### Local file tip

If Alt1 complains about local files, relaunch Alt1 with the launch option:

```
--allow-file-access-from-files
```

## Recommended combo

1. Keep this Cue Board open for the big visual banners.
2. Pair it with your own voice-callout setup (e.g. AfkWarden) the same way you did for Zamorak, if you use one for Sanctum.
3. Let auto-read fire the banner where a chat line exists, or press the matching number key / test button otherwise.

## Tips

- Keep chat timestamps on.
- Chat font size 12 works best.
- Interface scaling 100%.
- You can drag the app window wherever is convenient; the banner overlay appears in the middle-upper area of the game screen regardless.
- The Hard Mode toggle is a reminder note only — it doesn't change detection, since the confirmed chat lines are the same in both modes.

Good luck pushing enrage through the Sanctum!
