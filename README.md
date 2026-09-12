# Brik

Brick's ritual without the brick. One file, no backend, state in `localStorage`.

- `index.html` — the whole app. Open it anywhere, or add to Home Screen.
- `PROMPT.md` — the prompt that regenerates it from scratch.

## The trigger, three ways

Brick works because unlocking requires walking to a physical object. Brik keeps that
asymmetry without shipping hardware: **laying the brick is one press; lifting it needs a
key phrase that lives somewhere inconvenient.**

**A · Command.** Type `brik` to lock. Type the key phrase to unlock. `help` lists the
rest. Works from the phone keyboard, a Shortcut, or a desktop browser.

**B · NFC sticker (~$1, no app needed on tap).** Write `unbrik <your phrase>` as a Text
record to an NTAG215 sticker using NFC Tools. Stick it on the fridge, inside a drawer,
by the front door. iPhones read NDEF tags in the background — hold the top of the phone
to it and the phrase appears in a notification. Walking there *is* the friction.

**C · Shortcuts automation (real enforcement).** Shortcuts → Automation → NFC → scan the
tag → **Set Focus** (toggle) + **Copy to Clipboard** (the phrase). Run Immediately on,
Notify When Run off.

Worth being straight about: no web page can hide apps on iOS. Only Focus and Screen Time
can. So the tag flips Focus for the actual blocking, and Brik holds the clock, the
streak, the knocks, and the cost of quitting early.

## Hosting it yourself

Any static host works. Once it has its own origin, `?cmd=brik` and
`#unbrik <phrase>` drive it from a URL, so an NFC tag or a Shortcut can toggle it
directly with no typing.
