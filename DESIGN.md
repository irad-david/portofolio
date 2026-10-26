# Design notes

The site is built on one idea: **David's work, shown as the infrastructure he patches together.** It uses a light documentation-paper ground with one dark rack object, labels styled like equipment tape, and cable colours that carry meaning. All tokens live in `:root` in `index.html`.

## Colour

| Token | Value | Role |
|---|---|---|
| `--paper` | `#F2F3EF` | page ground |
| `--paper-2` | `#E6E8E3` | banded sections (Selected work) |
| `--sheet` | `#FBFBF9` | cards, label tape, diagram stage |
| `--ink` | `#0E141B` | text, rules, buttons |
| `--ink-2` / `--ink-3` | `#38424C` / `#5A646E` | secondary / tertiary text (both ≥ 4.5:1 on paper) |
| `--rack` | `#15181C` | patch panel, contact section |
| `--yellow` | `#F2C230` | selection, readout port, focus ring on dark |

**Cable colour code.** Each `data-c` value sets `--cord` (and `--cord-strong` for thin lines on white). Use the same colour for a topic everywhere: ports, stack layers, tags, tabs and diagrams.

| `data-c` | Meaning |
|---|---|
| `blue` | Network & security |
| `green` | Servers & virtualisation |
| `orange` | Identity & access |
| `violet` | Cloud & Microsoft 365 |
| `white` | Monitoring |
| `grey` | Voice |
| `yellow` | Support |

Colour is never the only signal. Every swatch sits next to a text label.

## Type

- **Archivo** (variable, `wdth` 62–125). Display and section headings are set uppercase at `font-stretch: 72–78%`, weight 800, the way equipment labels read. Body text is regular width, 17px, line-height 1.6.
- **JetBrains Mono** is used only for data: port numbers, dates, SIP messages, rule lines. It is never used for decoration.
- There are no eyebrow labels above headings and no gradient text.

## Components

- **Label tape** (`.tape`): uppercase condensed text on `--sheet` with a soft offset shadow. Use it for asset tags, certificate codes and the Monitoring probe.
- **Port** (`.port`): a button containing a number, tape label, jack, LEDs and a coloured plug. Ports use a roving tabindex, so arrow keys move between them.
- **Diagram** (`.dg`): a 640×340 SVG on a 20px grid. Nodes are white boxes with a 1.5px ink stroke, and the key node is tinted with `--cord`. Flows are `.beam` paths with `pathLength="100"`.

## Motion

- **The one authored moment:** the hero entrance. The name rises, then the cables patch in one by one and their LEDs light.
- **Scroll-linked effects:** stack layers spread apart, and the experience cable draws.
- **Small feedback:** case-study crossfades, credential tapes "print", and the photo clip reveal.
- **Easing:** `[0.16, 1, 0.3, 1]` (expo out). Only transform, opacity, clip-path and stroke offsets are animated.
- **Reduced motion and fallbacks:** under `prefers-reduced-motion`, or if the script fails, the `.no-motion` class renders every final state immediately.
