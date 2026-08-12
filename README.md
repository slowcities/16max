# 16Max

A sixteen step sequencer with a note, a length, a loudness, a probability and a repeat count on every step. Built as a teaching instrument.

One HTML file. No install, no build step, no account, no cost. Open the link and it makes sound.

**▶ Play it here**

---

## Why this exists

[4LS](https://slowcities.github.io/4LS/) teaches how a sound is built. [ADrum](https://slowcities.github.io/adrum/) teaches rhythm played by hand. This teaches what happens when a machine keeps time instead of a person — and, more importantly, what a machine can do that a person cannot.

The lesson is not "a sequencer repeats a pattern." A device that repeats a pattern is a recording. The lesson is **Probability**: a step set to 60% plays six times in ten, so the pattern is never quite the same twice and yet is never random. That is a machine making decisions inside limits you set, which is a different musical idea from anything else in the suite and the reason this instrument exists.

Everything else on the panel is in service of hearing that clearly.

---

## What it is

Complete and working. What is built:

- Sixteen steps, five parameters each, with a live playhead
- Lookahead scheduler running on the audio clock
- Probability, ratchets, and ties
- Fill mode — hold steps to play them live over the running pattern
- A single monophonic voice derived from VCO 1 of 4LS, with a tempo-synced delay
- MIDI learn with soft takeover, covering the voice, the transport, and the Play and Fill buttons
- Seven presets
- The help system in six languages

The five non-English translations have not been reviewed by a native speaker.

---

## Languages

The help text is available in English, Español, 한국어, العربية, 中文, and 日本語. The language buttons appear on the start screen and again in the help bar once Help is on; the choice is remembered on that computer.

Translated: every help panel, the start screen, and the mode line under the grid. Arabic help reads right to left, though the grid itself does not flip — a step sequence runs left to right on every instrument in the world.

Control labels stay in English on purpose — Note, Gate, Velocity, Probability, Division, Cutoff, Attack. That vocabulary is shared across sequencers worldwide, so a student who learns it here can read the panel on any hardware sequencer in any country. Preset names stay in English for the same reason.

---

## Getting started

1. Open the link. Click **Start the sequencer** — browsers require a click before audio can begin.
2. Load a preset from the dropdown at the top right and press **Play**.
3. Turn on **Help** to read what each section does.
4. Change one thing and listen to what moved.

Headphones recommended. Start with the volume moderate.

---

## The sequence

Sixteen steps in two rows of eight. Tap a step to select it; tap the selected step again to switch it on or off. The detail panel below edits all five of its parameters.

Editing one step at a time is a deliberate compromise. Sixteen steps times five parameters is eighty values, and a grid showing all of them is unreadable on a phone. The grid shows what you need at a glance — on or off, the note, the repeat count, and the probability if it is below 100% — and the detail panel holds the rest.

### The five parameters

**Note** — A0 to C8.

**Gate** — how long the step holds, from a short blip to the full slot. At maximum it reads **Tie**: the note does not release, and the next step changes pitch without restarting the envelope.

**Velocity** — 1 to 127. Louder, and also brighter if Vel → Cutoff is up.

**Probability** — the chance the step plays at all. At 100% you have a pattern. Below that you have a pattern that decides.

**Division** — ratchets. A step set to ×4 fires four evenly spaced times inside its own slot without changing the length of the bar.

### Transport

**Tempo** 40 to 240 BPM. Steps are sixteenth notes.

**Last step** is where the pattern loops back. Setting it to anything other than 16 is the quickest way to hear an odd meter — seven steps against a four beat count takes fifteen bars to come back around. There is no time signature control because Last step already does that job better.

The blue marker is the playhead. A step outlined in pink was skipped by its own probability — the playhead arrives, and nothing sounds. That visible skip is the point.

---

## Fill

Press **Fill**, then hold steps to play them live over the running pattern. Held steps cycle in grid order, one per slot, while the clock keeps its own time. Release and the pattern resumes exactly where it would have been.

| Input | How |
| --- | --- |
| Computer keyboard | **Q A W S E D R F T G Y H U J I K** — laid out like a piano across two rows, steps 1 to 16 |
| Touch | Hold steps directly on the grid. Multi-touch works, so several at once is fine |
| MIDI | Notes C2 to D#3 hold steps 1 to 16. Hold several to build a fill |

The grid edits when Fill is off and plays when Fill is on — the line beneath it always says which. The keys and pads only respond while Fill is armed, so there is never a mode the interface is not showing you.

A held step plays even if it is switched off in the pattern, since holding it is an explicit instruction. Probability still applies, so a held step at 40% will still skip sometimes.

---

## The voice

One oscillator, one filter, one envelope, taken from VCO 1 of 4LS. Deliberately small: this is a sequencer, and the voice is here to make the sequence audible rather than to be a second synthesizer.

**Shape** sweeps continuously from triangle through saw to pulse. **Width** shapes the pulse. **Cutoff** and **Resonance** are a low pass filter that will ring on its own when pushed. **Attack, Decay, Sustain, Release** shape each note. **Glide** slides from one pitch to the next instead of jumping — with Gate at Tie the notes join up and the slide is the only thing you hear move.

**Vel → Cutoff** is worth its own mention. Velocity raises the level, and this control also opens the filter with it, so a hard step is brighter as well as louder. That is most of what makes velocity feel expressive rather than technical.

### Delay

**Time, Feedback and Mix**, the same three controls ADrum uses, with one difference: Time is measured in beats rather than seconds. The choices run 1/32, 1/16, 1/8T, 1/8, dotted 1/8, 1/4, dotted 1/4 and 1/2, and they follow the Tempo when you change it.

This is deliberate. ADrum has no clock, so a free-running delay is right there. Here there is a strict grid, and a delay drifting across it mostly produces mud. Measured in beats, the echoes land on the steps instead — six of the eight divisions fall exactly on the sequence, and the two that do not, 1/32 and 1/8T, are the interesting ones to reach for when you want the echoes between the steps rather than on them.

A dotted 1/8 against straight sixteenths is the classic cascading pattern, and it is the fastest way to show a student that an echo can be a compositional device rather than an effect.

Feedback is capped and the write is limited, so a delay tuned to reinforce itself gets loud and then sits rather than climbing without end. Every preset starts dry except Three octave minor and Ratchets.

### MIDI learn

Click MIDI learn, click a control, then move the knob, fader or pad you want. Assignments appear as a small CC number and are saved on that computer.

Assignable:

| Target | Behaviour |
| --- | --- |
| Any voice or delay slider | Continuous, with soft takeover |
| Tempo | Continuous, 40 to 240 BPM |
| Last step | Continuous, 1 to 16 — sweeping the pattern length while it runs is a real technique |
| Play | Toggles on a press, ignores the release |
| Fill | Momentary: armed while the pad is held, so a fill can be played with one hand |

Sweeping the Cutoff by hand while the sequence runs is most of what makes this instrument fun to perform. Putting Last step on a second knob is the other half — shortening a pattern from 16 to 7 mid-phrase changes the music far more than any filter sweep.

Sliders use **soft takeover**: after a reload or a preset change the hardware is no longer where the slider is, so it does nothing until you sweep it onto the current value and pick it up. A pink tick on the track shows where the hardware is sitting. This means loading a preset never gets it yanked out of shape by a knob in the wrong position.

The step parameters are deliberately not assignable. They are edited rather than performed, and eighty of them on a controller would make the mapping list useless.

---

## Presets

Seven worked examples, each demonstrating one idea, all built from the same panel.

**Init** — four downbeats. A clean place to start.

**Two octave major** — C major from C4 to C6. Fifteen notes, so Last step sits at 15. A two octave scale does not fit a sixteen step grid, and hearing why is the lesson.

**Three octave minor** — A minor pentatonic from A3 to A6. Five notes to the octave means three octaves land on exactly sixteen steps. The contrast with the preset above is the point of having both. A dotted 1/8 delay turns the ascending run into a cascade.

**Probability** — steps 1, 5, 9 and 13 are certain; everything between them sits between 20% and 60%. The skeleton holds while the filigree rearranges itself, about nine notes of sixteen on any given pass.

**Velocity and filter** — one note, sixteen times, velocity climbing from 8 to 127 with the cutoff starting at 220 Hz. Nothing changes but how hard it is struck.

**Ratchets** — divisions climbing 1, 2, 3, 4 so the repeats are countable. Forty-one hits per bar instead of sixteen, with a 1/16 delay doubling them again.

**Tie drone** — every gate at Tie, so the sequence never lets go. One continuous note with pitch, loudness and brightness stepping underneath it. This only sounds at all because Sustain is up; pull Sustain to zero and the whole thing goes silent, which is itself the clearest demonstration of what Sustain does.

Patterns are not saved between sessions. This is deliberate: it keeps the file self-contained and keeps students building rather than recalling.

---

## Teaching with it

**What a sequencer actually is.** Load Probability and watch the playhead rather than listening. Steps light up and do not sound. Ask what "the pattern" means when it is different every time round.

**Why scales do not fit machines.** Two octave major needs 15 steps; three octave minor needs exactly 16. Same grid, different scale, completely different relationship to the bar.

**Odd meter for free.** Take any preset and drop Last step to 7 or 5. Count along and find where it comes back around.

**What velocity really does.** Load Velocity and filter. One note, sixteen times. Then turn Vel → Cutoff to zero and play it again — now it only gets louder, and the difference between loud and expressive is audible in one move.

**What a tie is.** Load Tie drone, then pull Sustain to zero and hear it vanish. Put it back and raise Glide instead.

**Ratchets against probability.** Set a step to ×4 and 50%. It either fires four times or not at all — the roll happens once per step, not once per hit.

**An echo is not an effect.** Load Two octave major, set Delay Mix to about 0.4, then walk Time from 1/16 up to dotted 1/4. Each division rewrites the rhythm of a scale that never changed.

**Playing the length.** Put Last step on a hardware knob and sweep it while the pattern runs. Students hear a phrase get cut short and turn over against the count — the same lesson as odd meter, but performed rather than set.

---

## Requirements

Any current browser: Chrome, Edge, Firefox, or Safari 14.1+. Works on phones and tablets.

MIDI requires a browser with WebMIDI (Chrome and Edge; Firefox and Safari do not currently support it). This covers both fill triggering and MIDI learn. Everything else works everywhere.

---

## Playing with others

There is no network sync, and this is a decision rather than a missing feature. Browsers cannot find each other on a local network without a server standing in the middle, and a classroom performance should not depend on wifi that will fail at the worst moment.

The arrangement that works: one device runs 16Max into the PA and everyone else plays 4LS and ADrum by hand over it. The sequencer becomes the drummer. That is how a band works, and it makes the timekeeper a real musical role rather than a technical workaround.

If two students both want patterns running, starting them together by hand gets within a few tens of milliseconds and they will drift apart over a minute or two. Fine for an exercise, not for a recital.

---

## Hosting it yourself

The whole instrument is one file. Fork this repo, enable GitHub Pages in Settings → Pages, and it is live.

**Do not open the file directly from your hard drive.** A `file://` page has no real origin, and browsers refuse to load the AudioWorklet that generates the audio. The panel will appear and nothing will make sound. Serve it over HTTP instead — GitHub Pages, or locally:

```
python3 -m http.server 8000
# then open http://localhost:8000
```

---

## Under the hood

**The clock is `AudioContext.currentTime`, never a timer.** A timer decides only *when to look ahead*; every note is stamped with an exact audio clock time and placed on the right sample inside the worklet. This is why the pattern does not drift when the browser is busy, and why a phone stuttering for a moment makes the animation late but not the music. Measured over four bars, the interval error is zero.

**Probability is rolled once and cached.** A step needs to know whether the next step will fire before it can decide whether to tie into it. Rolling twice would let a step tie into a note that then never happens, leaving a hung note — two hundred simulated runs, zero hangs.

**A step cannot tie into itself.** Holding one step in a fill, or setting Last step to 1, would otherwise leave the note-off unsent forever: the envelope never retriggers and decays to the Sustain level. Such a step falls back to a 98% gate instead.

**Ties do not retrigger, ratchets do.** A tied step changes pitch with the envelope left running — the same last-note-priority behaviour 4LS has in Mono. Repeats inside a ratcheted step always re-articulate, otherwise a ratcheted tie would collapse into one long note and the repeats would vanish silently.

**The delay is measured in beats and resolved to seconds at the last moment.** The panel holds a division; the engine is told a duration, recalculated whenever the tempo moves. The buffer is sized once for the worst case — two beats at 40 BPM is three seconds — and never reallocated, so changing tempo mid-performance allocates nothing.

**Envelope times are calibrated to the labels.** A Decay reading 0.5 s falls to 1% of its range in 0.5 s. Same correction as 4LS and ADrum, inherited deliberately so the bug that shipped in the first 4LS build cannot reappear.

**Oscillators are PolyBLEP band-limited** and the filter is TPT state-variable, with a saturator in the resonant path so high resonance settles rather than running away. A limiter sits on the master, linear below its knee so ordinary playing passes through untouched.

---

## Design principles

- **Zero friction.** One file, no build, no install, no accounts. If a student can open a link, they can use it.
- **Visible consequence.** Every control shows its effect somewhere on screen, and every label reports what the engine actually received — including the skipped steps.
- **Restraint.** One instrument built well. One voice, one filter, no second oscillator, no song mode, no pattern chaining.
- **Free access.** The barrier this removes is cost. Reintroducing it would defeat the point.

---

## License

Released under CC BY 4.0. Use it in your classroom, your workshop, your program. Modify it, translate it, rebuild it, fold it into your own curriculum, share it however you like. The only condition is attribution.

---

## Companion projects

**[4LS](https://slowcities.github.io/4LS/)** — a subtractive synthesizer you can see through.

**[ADrum](https://slowcities.github.io/adrum/)** — four percussion voices with AD envelopes, played by hand.

**[Video Surfer](https://slowcities.github.io/video-surfer/)** — a browser-based experimental video synthesizer in the Rutt/Etra lineage.
