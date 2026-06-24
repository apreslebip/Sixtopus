---
title: Sixtopus — Changelog
---

# Changelog

Every notable change to Sixtopus, written down so you don't have to guess.

## [2.1.1] — 2026-06-24

A correctness pass — and a rethink of what mute should do to pitch.

- **Dive B's jacks were swapped.** V/Oct and Gate on Dive B now match the panel
  labels (inner = V/Oct, outer = Gate), mirroring Dive A. If you'd patched around
  it, you'll want to swap the cables back.
- **Mute holds the note now.** Muting a DIVE channel freezes its V/Oct on the last
  played note instead of dropping to 0V — your oscillator stays put instead of
  slamming to the bottom. The playhead keeps running silently, and the pitch picks
  back up, in sequence, the moment you un-mute. (This reverses the 2.1.0 behaviour,
  which dropped the CV — turns out a held note is the kinder default.)
- **Muted tracks step out of the way.** You can't select a muted track for editing
  anymore; muting the one you're editing clears the selection until you pick another.
- **The V/Oct LED reads pitch.** It's now a steady level indicator — brightness
  tracks the held voltage — rather than a per-note flash.

— Après le bip

## [2.1.0] — 2026-06-17

A polish pass. Nothing about the sound engine changed — but the module reads
clearer and mutes the way you'd expect.

- **Mute now cuts the pitch too.** Muting a DIVE channel (or the whole module)
  drops its V/Oct to 0V along with the gate, instead of leaving your oscillator
  frozen on the last note. Silence means silence.
- **Muted means dark.** A muted track's button simply turns off now, instead of
  glowing red — just like a single-colour panel LED would. Global mute darkens
  all six at once; unmute and every track returns to exactly the state it was in.
- **Channels have names.** The buttons and the Mute menu now read **Dive A,
  Trigger 1–4, Dive B** instead of "Channel 1…6". No more counting.
- **Scales in plain English** — Dorian, Phrygian, Lydian, Mixolydian, Locrian.
- **A bigger, cleaner panel** — components scaled up for easier reading and
  handling, and the little 3-way switches got a crisper look.

— Après le bip

## [2.0.0] — 2026-06-14 🐙

Hello world. This is the first time Sixtopus leaves the tank.

It's a beta — which means it's real, it works, and it would genuinely love
for you to try to break it. Here's what's in the box:

- **Two DIVE channels** — two melodic minds, each running a Turing Machine that
  loops, drifts and mutates on its own. SPAN, MUTATE, SEED, LENGTH (2–16).
  Set it going, then spend the rest of the evening arguing with it.
- **A custom piano keyboard** — pick your notes on a real keyboard layout,
  black keys up top, white keys below. It opens already showing the scale you
  came from, so you're never staring at a blank octave wondering where C went.
- **Four trigger channels** — drums, gates, mayhem. TRIG 4 rolls the dice on
  every step (CHANCE), so your hats breathe and your kick ghosts when it feels like it.
- **One clock, six channels, eight time divisions** (/1 … /16) and a global
  SWING — a whole band out of a single pulse.
- **CV smeared all over it** — push Span, Mutate or Bypass TM from anything that wiggles.
- **Mute** the whole thing or one voice at a time, while the sequences keep
  evolving behind your back. Unmute and see what it got up to.
- **Save, close, reopen** — and it's exactly where you left it, down to the
  precise Turing Machine registers. Your loops stay your loops.

Found something weird? Perfect. That's the entire point of a beta — tell us, we're quick.

— Après le bip
