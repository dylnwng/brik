# Brik — build prompt

Paste the block below into Claude (on the iPhone app, claude.ai, or Claude Code) and you
get the whole app back from nothing. It's the same text that ships inside the app under
"Rebuild Brik from scratch".

---

Build me "Brik" — a single-file HTML app, no build step, no backend. It is Brick (the
NFC-brick focus app) with the physical brick replaced by a key phrase.

Behaviour:
- Two states: OPEN and BRICKED. A running clock shows time in the current state.
- Laying the brick is easy: press and hold the big slab for ~1s, or type "brik".
- Lifting it is deliberate: you must type a 4-part key phrase (e.g. mortar-kiln-clay-42)
  that the app generates. I keep the phrase on an NFC sticker away from my desk, so
  unlocking means physically walking to it.
- Escape hatch: hold a button for 8 seconds to break out. Costs one of 3 weekly passes
  and resets the streak. Log it as "broke out".
- Blocklist of apps. Tapping a blocked app while BRICKED shows a full-screen brick wall
  and counts a "knock".
- Stats: day streak, time bricked today, knocks this session, passes left.
- Ledger of the last 6 sessions: duration, knocks, broke-out flag.
- Commands: brik / <phrase> / status / block <app> / allow <app> / key / help / wipe.
- Everything in localStorage. Works offline. Add-to-Home-Screen friendly.
- Also honour ?cmd= and #hash triggers so a Shortcut can drive it.

Design: masonry, not startup. Fired-clay red (#A63A22), cool mortar grey (#E3E2DC),
near-black with a red-brown bias (#17120F). Archivo variable (expanded + heavy) for the
state word, Sometype Mono for every number and label. The slab turns clay-red with a
running-bond brick pattern when BRICKED — that state change is the whole identity.
Light and dark themes via CSS custom properties.

Include a setup panel explaining how to write the phrase to an NTAG215 sticker with NFC
Tools, and how to pair it with an iOS Shortcuts NFC automation that toggles a Focus mode
— since only Focus/Screen Time can actually hide apps on iOS.
