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
| **Playable ad** | an interactive ad for a mobile game, built to the network's size limits | 1–2 weeks | **USD 2,500 – 5,000** each |
| **Web build audit** | a per-file inventory of your exported build, measured as transfer size, and the ordered list of what to cut with the megabytes each saves. No access to your source | 3 business days | **USD 1,200** |
| **Audit + fixes** | the audit, then the fixes applied in your project and the build measured again | 5 business days | **USD 2,400** |
| **Catalogue or platform** | many titles, or a pipeline that publishes other people's games: the size rules become a gate in CI | scoped together | **from USD 4,000** |
| **Dedicated** | a Godot engineer who also draws, on your team | monthly | **USD 6,000 – 8,000 / month** |

Prices are fixed per scope and agreed before any work starts.

## What the work looks like

- **[godot-web-build-budget](https://github.com/zednaked/godot-web-build-budget)** —
  five production web builds, each 48% lighter or more with no assets deleted,
  and the first one measured again a month later with 3% left to give.
  What was actually in the `.pck`, why the obvious fix made it bigger, and a
  7 MB file nothing reads. Became
  [godot-proposals#15505](https://github.com/godotengine/godot-proposals/issues/15505).
- **[godot-i18n-that-holds-up](https://github.com/zednaked/godot-i18n-that-holds-up)** —
  12 locales, 3,673 translation pairs measured: buttons expand at a p95 of 2.00x,
  and `.length` lies for Hindi, Nepali, Arabic and German.
- **Games in the browser:** Ciberteia (multiplayer, authoritative backend) and
  Rinha (real-time strategy; one web performance pass took the opening from
  1,565 draw calls a frame to 29, and a 700-unit late game from 36 to 57 fps)
  at [zedcave.itch.io](https://zedcave.itch.io).
- **Art and illustration:** [zednaked.github.io/portfolio](https://zednaked.github.io/portfolio/).
- **Tools:** [ZGT](https://github.com/zednaked/zgt), a terminal inside the Godot
  editor; [omarchy-zero](https://github.com/zednaked/omarchy-zero); two plugins
  that passed review in the Omarchy marketplace.

## What changed after I looked

Three open-source projects, three maintainers who read a measurement of mine and
shipped a change. All of it is public in their repos.

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

## How to start

Write to **zednaked@gmail.com** with what you have: a build link, a design, or
a problem. I answer with what I would measure first and a fixed quote. For an
audit, a link to the published build is enough.
