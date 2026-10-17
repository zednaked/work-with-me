# Work with me

Thiago Gonçalves · Godot engineer, 2D artist and animator · Curitiba, Brazil ·
remote, any timezone · **zednaked@gmail.com**

I build games for the browser and make them fit inside the budget somebody else
set: download size, frame time, twelve locales, a phone that has to open it.
In the last year that was a catalogue of 20+ commercial titles shipped to the
web, as the sole front-end engineer, with the art and animation done in the same
hands. Client work is under NDA; the method and the measurements are public.

## What I take on

| | what you get | time | price |
|---|---|---|---|
| **Web game, start to finish** | a casual browser game built in Godot, one core mechanic, with the art and animation included, shipped under a size budget you can check | 4–6 weeks | **USD 8,000 – 15,000** |
| **Bring a Godot game to the browser** | your existing project exported to the web and made to load: import settings, export filter, loading, localization, measured before and after | 2–3 weeks | **from USD 4,000** |
| **Playable ad** | an interactive ad for a mobile game, built in PixiJS as one HTML file under the network's cap, with the byte inventory: library, art, and the base64 tax ([measured example](https://github.com/zednaked/playable-budget)) | 1–2 weeks | **USD 2,500 – 5,000** each |
| **Web build audit** | a per-file inventory of your exported build, measured as transfer size, and the ordered list of what to cut with the megabytes each saves. No access to your source | 3 business days | **USD 1,200** |
| **Audit + fixes** | the audit, then the fixes applied in your project and the build measured again | 5 business days | **USD 2,400** |
| **Catalogue or platform** | many titles, or a pipeline that publishes other people's games: the size rules become a gate in CI | scoped together | **from USD 4,000** |
| **Dedicated** | a Godot engineer who also draws, on your team | monthly | **USD 6,000 – 8,000 / month** |

Prices are fixed per scope and agreed before any work starts.

## What the work looks like

- **[godot-web-build-budget](https://github.com/zednaked/godot-web-build-budget)** —
  sixteen production web builds, cut 23% to 76% with no assets deleted, the
  range set by how much of each pack was lossless art; the first one measured
  again a month later with 3% left to give.
  What was actually in the `.pck`, why the obvious fix made it bigger, and a
  7 MB file nothing reads. Became
  [godot-proposals#15505](https://github.com/godotengine/godot-proposals/issues/15505).
  The sixth edition treats memory as a second budget: an iPhone build losing its
  WebGL context went from 561 to 217 MB of live texture, because the GPU keeps
  every frame as full RGBA no matter how small the PNG was.
- **[playable-budget](https://github.com/zednaked/playable-budget)** —
  a playable ad in one HTML file at 630 KB, 31% of Meta's 2 MB cap, every byte
  accounted for: what the library, the art and the base64 inlining each cost,
  and why an empty Godot web export (39.8 MB) can't enter the format.
  [Play it](https://zednaked.github.io/playable-budget/).
- **[godot-i18n-that-holds-up](https://github.com/zednaked/godot-i18n-that-holds-up)** —
  12 locales, 3,673 translation pairs measured: buttons expand at a p95 of 2.00x,
  and `.length` lies for Hindi, Nepali, Arabic and German.
- **[Jangada](https://github.com/zednaked/jangada)** — alternative firmware in
  C++ for the M-VAVE FM-1, a €70 pocket synth: thirteen real-time synth engines
  (one a 6-operator FM that reads Dexed patches), 8 voices over 4 tracks, a
  64-step sequencer, and a [Studio](https://zednaked.github.io/jangada/webapp/studio/)
  that plays it in the browser. Version 1.0 and 352 firmware downloads in its
  first ten days,
  listed in the community's one-click FM-1 Firmware Hub; its ratchet went
  upstream into [Felucca](https://github.com/hugelton/Felucca) 1.0.5 with me as
  co-author. 1.0.1 opened an editor protocol a DAW or a mixer can drive, after
  a user asked to save the synth's edit buffer with their projects; Nirbija,
  below, is the first host that speaks it.
- **[Nirbija](https://github.com/zednaked/Nirbija)** — a Linux mixer that is also
  an instrument, in C++ and Qt: LV2, CLAP and VST3 over JACK or PipeWire, with a
  drone synth, sampler, looper and sequencers built in. **Since 0.6.0 it drives
  the FM-1 running Jangada: I wrote both ends, the firmware on the device, the
  host on the computer, and the SysEx protocol between them.** The FM-1 is a
  strip of its own: its project saved in the session, its four tracks in an
  editor, and a scene that swaps a track's whole sound on the bar line.
- **Games in the browser:** Ciberteia (multiplayer, authoritative backend) and
  Rinha (real-time strategy; one web performance pass took the opening from
  1,565 draw calls a frame to 29, and a 700-unit late game from 36 to 57 fps)
  at [zedcave.itch.io](https://zedcave.itch.io).
- **Art and illustration:** [zednaked.github.io/portfolio](https://zednaked.github.io/portfolio/).
- **Tools:** [ZGT](https://github.com/zednaked/zgt), a terminal inside the Godot
  editor; [godot-unreachable](https://github.com/zednaked/godot-unreachable),
  which lists the files a Godot project ships that nothing can reach; [omarchy-zero](https://github.com/zednaked/omarchy-zero); two plugins
  that passed review in the Omarchy marketplace.

## What changed after I looked

Seventeen projects, seventeen people who read a measurement of mine and shipped
a change. All of it is public, in their repos, their replies or their own posts.

- **[Audible Field](https://audible-field.vercel.app)**, a spatial sound piece by
  Gary Boodhoo (formerly ZeniMax, LucasArts, EA). Most of the first load was
  24-bit stereo WAV, and the engine folds every bed to mono before its own
  panner, so the second channel never reached anyone's ears. He moved runtime
  audio to mono Opus and
  [wrote it up himself](https://www.linkedin.com/feed/update/urn:li:activity:7515588700316110848/):
  roughly 90% less audio transferred. First load, measured: **32.6 → 1.86 MB**.
- **[Bachy](https://github.com/Paul-M-Kallarackal/Bachy)**, a keyboard-first file
  manager for Hyprland. I measured what its required dependencies pulled in over
  a plain Arch base and where the weight came from: the whole Qt WebEngine, only
  for PDF previews. The next morning the PDF, media and font support were
  optional, with a fallback and a regression test: **564 MiB less**, two thirds of
  the total. The maintainer wrote it up in
  [DEPENDENCY-AND-STARTUP-AUDIT.md](https://github.com/Paul-M-Kallarackal/Bachy/blob/main/docs/DEPENDENCY-AND-STARTUP-AUDIT.md).
- **[lumen](https://github.com/blackopsrepl/lumen)**: an accessibility report,
  [lumen#2](https://github.com/blackopsrepl/lumen/issues/2), on a Qt tree that
  looks populated to the accessibility API when it is structurally empty. It
  was implemented and shipped in v0.13.6 and v0.13.7.
- **[zenbook-duo-hyprland](https://github.com/laithm/zenbook-duo-hyprland)**: the
  display state was lost on every Hyprland config reload. It was
  [fixed within the hour](https://github.com/laithm/zenbook-duo-hyprland/commit/dd626ef7f46b807626bc547f7d78e8ba508e7ae4),
  and I reviewed the commit.
- **[EchoMind](https://github.com/sewox/EchoMind)**, an on-device meeting
  transcriber: system audio was recorded from the output device chosen at the
  start, so switching to headphones mid-meeting silently dropped the other side
  of the call. It now follows the device on Linux and Windows,
  [PR #111](https://github.com/sewox/EchoMind/pull/111), released in v0.2.16
  the next day.
- **[pipewire-auto-router](https://github.com/klasnalol/pipewire-auto-router)**:
  the watcher polled every two seconds, so a new stream played on the default
  device for up to two seconds before it was routed. 0.2.1 reacts to PipeWire
  graph events instead ([commit](https://github.com/klasnalol/pipewire-auto-router/commit/8c2b8e13bdcd46cc98162f944602ab4d586d8e78)).
- **[CrunchyPy](https://github.com/Yahiake/CrunchyPy)**, a neural guitar amp in
  JUCE: in the author's previous plugin the network, trained at 48 kHz, ran at
  whatever rate the host used, so at 96 kHz the mid scoop moved from about
  1 kHz to 2 kHz. His next one resamples to 48 kHz around the model and reports
  the latency to the host.
- **Orb Skirmish**, a browser multiplayer arena (Phaser + Colyseus). Alone in a
  match, the room sent a full ~6.3 KB snapshot 20 times a second. The developer
  moved to Colyseus Schema the same day and measured it in production, one guest
  and seven bots: **7.6 → 0.26 MB a minute**, still at 20 updates a second.
- **The Last Bite**, a three.js game: 9.7 MB of the 22 MB first load was a
  second copy of the character mesh and textures, there only to carry a 20 KB
  run clip. Shipping the clip alone took the first load to **12.4 MB**.
- **Sky Soarer**, hand tracking with MediaPipe in the browser: the camera path
  carried a palm detector the chosen model never uses. A lite-only data file
  with a checksum guard took it **from 7.8 to 5.4 MB**.
- **A cache-hierarchy visualizer** in three.js with a C++ IDE in the browser:
  nginx served the bundle uncompressed, because its `gzip_types` covers only
  HTML by default. Compression on, the IDE loaded lazily and three.js in its own
  bundle took the initial JavaScript **from 671 KiB to 140–180 KiB**.
- **Dust**, an idle game from Mob Machine: progress only counted while the tab
  was in front, so four minutes in the background earned 0.14 of a resource
  that pays 1.0 a second. Fixed the next day.
- **[ink-of-the-forgotten-path](https://www.npmjs.com/package/ink-of-the-forgotten-path)**,
  a martial-arts motion package: strike speed in m/s came from normalized screen
  coordinates times a fixed constant, so it changed with distance to the camera.
  v0.1.2 uses metric world landmarks by default and labels what the HUD measures.
- **[Kiln](https://github.com/MPanknin/kiln-render)**, a WebGPU volume viewer for
  OME-Zarr microscopy data: the texture atlas was always `r16float`, so a 16-bit
  volume kept 7,169 of its 65,536 levels and the bright half moved in steps of
  32. Two days later the atlas stores uint16 losslessly
  ([commit](https://github.com/MPanknin/kiln-render/commit/1649067)).
- **Neutro Dance**, a three.js and Web Audio dance app: every song's decoded PCM
  stayed in memory, about 300 MB across five tracks on a phone. The developer
  measured 48 to 75 MiB a track himself and shipped the fix the same day: only the
  playing track keeps its PCM.
- **Circat Thought**, a local AI sampler plugin in JUCE: the browser preview read
  the WAV from disk inside the audio callback. v1.1.2 decodes the clip into
  memory on the message thread, so the audio thread never touches the disk.
- **[Xenhusk Mixer](https://github.com/xenhusk/xenhuskmixer)**, a Windows
  mixer in JUCE: below its threshold the denoise dropped to 0.08 gain in a
  single sample, a 22 dB step with no ramp, so word onsets and tails clicked.
  It now fades over about 5 ms through the same smoother the gate uses, with a
  test that checks the first quiet sample and the settled gain.

## How to start

Write to **zednaked@gmail.com** with what you have: a build link, a design, or
a problem. I answer with what I would measure first and a fixed quote. For an
audit, a link to the published build is enough.
