# 🐙 Sixtopus

**Dual Turing Machine Sequencer for VCV Rack 2 — 20HP**

Sixtopus is a generative sequencer built for patches that think for themselves. Two independent melodic voices, four trigger channels, one shared step grid — and a Turing Machine at the heart of each melody that evolves, mutates, and surprises you in ways you'd never program by hand.

Set a few parameters. Patch it up. Listen. Respond. That's the workflow.

---

## ⬇️ Download & install

1. From the **[latest release](https://github.com/apreslebip/Sixtopus/releases/latest)**, download the `.vcvplugin` for your platform:
   - macOS Apple Silicon → `…-mac-arm64.vcvplugin`
   - macOS Intel → `…-mac-x64.vcvplugin`
   - Windows → `…-win-x64.vcvplugin`
   - Linux → `…-lin-x64.vcvplugin`
2. In VCV Rack 2, open **Help → Open user folder**. A `Rack2` folder opens.
3. Move the downloaded file into the subfolder matching your platform — `plugins-mac-arm64`, `plugins-mac-x64`, `plugins-win-x64` or `plugins-lin-x64` (delete any older Sixtopus there first).
4. Restart Rack. It extracts and loads the plugin on launch — Sixtopus appears under the **Après le bip** brand.

Free to use. Full **[manual](https://apreslebip.github.io/Sixtopus/manual)**.

---

## 🎛️ Two DIVE channels — your melodic voices

Each DIVE channel (A and B) runs a **Turing Machine** — a looping shift register that generates evolving pitch sequences. The same loop plays over and over, but slowly drifts and transforms depending on how much mutation you allow.

- **SPAN** — controls the pitch range, from tight and chromatic to sweeping across five octaves
- **MUTATE** — the heart of it all. Fully left: the loop is locked. Fully right: pure randomness. In between: a melody that breathes and evolves on its own
- **SEED** — randomises the register instantly. Hit it until something clicks
- **LENGTH** — 2, 3, 4, 5, 6, 8, 12, or 16 steps before the loop repeats

> The Turing Machine always advances — even on silent steps. The pattern keeps evolving even when a voice is quiet.

Each DIVE channel outputs a quantized **V/Oct** and a **Gate**. The V/Oct holds its last value between notes, so your oscillator never drops to zero.

---

## 🥁 Four trigger channels

TRIG 1–4 are straightforward step sequencers — each active step sends a 1ms trigger pulse. Patch them to drums, envelopes, anything that responds to a gate. Program each pattern independently from the shared 16-step grid.

**TRIG 4 has a CHANCE control** — a probability knob that randomly skips active steps. A four-on-the-floor kick at 65% chance suddenly has ghost beats and occasional drops. You didn't program that. The module found it.

---

## 🎹 Scale quantizer

Seven built-in scales plus a **Custom mode** where the step grid becomes a chromatic keyboard — light up exactly the notes you want (C through B), and the quantizer locks to those pitches. Each DIVE channel has its own independent scale.

Empty custom scale = quantization bypassed. The raw Turing Machine CV passes through unmodified.

> Pentatonic (C, D, E, G, A) at high MUTATE is almost cheating — every random combination sounds musical.

---

## ⏱️ Swing, divisions, reset

**SWING** delays every odd step up to 50% of the clock period. One knob, full band shuffle.

**Time division** — right-click any channel button to set an independent clock rate from /1 to /16. Set DIVE A at /1 and DIVE B at /3 and watch them drift in and out of phase in ways you'd never write yourself.

**RESET** — a rising edge snaps all channels back to step 1. Clean sync, every time.

**Color-coded channels** — the six illuminated channel buttons tell you what's what at a glance: 🟢 green for the two DIVE voices, 🟡 yellow for the four trigger channels, 🔴 red when a channel is muted. Unselected channels blink in their colour each time they play a step, so you can watch all six work while editing one.

**Jack LEDs** — a 3mm LED above every jack flashes with activity: 🟢 green on the V/Oct outputs, 🟠 orange on the gates and triggers, 🟡 yellow on CLOCK, 🔴 red on RESET.

---

## 🔀 CV modulation

Patch any CV source (±10V) into **CV IN**, attenuate it with **MOD ATT**, then route it to **Span**, **Mutate**, or **Bypass TM** — for either DIVE A, DIVE B, or both.

**Bypass TM** is a special mode: the external CV replaces the Turing Machine output before the quantizer. Play Sixtopus from a keyboard. Use an LFO for slowly sweeping pitches. The Turing Machine keeps running in the background — switch back any time.

---

## 🔇 Mute

**Short-tap MUTE** to silence everything instantly — tap again to bring it back (it's a latched state, saved with your patch). **Hold MUTE and press a track** to mute/unmute that individual voice — holding it on its own never mutes the module, it just turns the channel buttons into per-track mute toggles (also available from the right-click menu). A muted track lights up **red** on its button. The sequences keep evolving while muted — unmute and drop back into whatever the module has been up to.

---

## 🔌 Inputs / Outputs

| Jack | Description |
|------|-------------|
| **CLOCK** | 1 pulse = 1 step |
| **RESET** | Returns all channels to step 1 |
| **CV IN** | Modulation input (±10V) |
| **VOCT A/B** | Quantized pitch (0–5V) |
| **GATE A/B** | 10ms gate on active steps |
| **TRIG 1–4** | 1ms trigger on active steps |

---

## 🛠️ Building from source

```bash
# Requires VCV Rack 2 SDK
git clone https://github.com/apreslebip/Sixtopus
cd Sixtopus/vcv
make install
```

---

## 📖 Manual

Full documentation with patching ideas, workflow tips, and everything explained in detail → [docs/manual.md](docs/manual.md)

---

## 📄 License

Sixtopus is **freeware** — free to download and use, not open source. © 2026 Après le bip. See [LICENSE](LICENSE).
