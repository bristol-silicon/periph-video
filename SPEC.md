# Peripheral spec: Video

> Copy this file, fill in every section, and open a pull request.
> Your team's game team (AND) and integration team (OR) must approve it **before** you write any Verilog.
> After the December spec freeze, changes need a `spec-change` issue (see CONTRIBUTING.md).
>
> **New to this?** Read [writing-your-spec.md](https://github.com/bristol-silicon/briss-docs/blob/main/writing-your-spec.md) and the worked [example spec](https://github.com/bristol-silicon/briss-docs/blob/main/example-spec.md) first.

## 0. Start here: answer these on paper first

1. What does the game need to **tell** this peripheral? → your write registers
2. What does the game need to **ask** it? → your read registers
3. What does it do **on its own**, without the CPU? → §4 Behaviour
4. What **events** does the game need to hear about, and how does it say "got it"? → status flags
5. What is everything **after reset**? → reset values
6. Which **pins** does it need? → §2 Pins
7. What's the **smallest useful version**? → v0.1 / v0.2
8. How will you **prove it works**? → §5 Checks

**Questions to think about for this peripheral** (hints, not answers; you decide):

- What resolution and how many colours? You only have 8 output pins, and VGA needs sync signals too.
- How many sprites, how big, and where does their picture data live (registers? a small memory?)
- Does the game need to know when a frame finishes, so it can move things without flicker? (e.g. a frame-done flag)
- Text overlay: how many characters, and where does the font come from?
- The enemy grid (NOT team) lives in this repo too. Agree its registers with NOT.
- Look at existing TinyQV video peripherals on Tiny Tapeout for ideas. Video is the biggest block on the chip, so plan v1.0 small.

Delete this section once the rest is filled in.

| | |
|---|---|
| **Team / sub-group** | XOR / VGA timing · Sprite · Text overlay |
| **Owners** (2 names) | |
| **Type** | Full |
| **Slot number** | Given by OR |
| **Size budget** | Given by OR, in cells |
| **Status** | Draft |

## 1. Purpose

One or two sentences: what does this peripheral do for the game?

## 2. Pins

Only pins listed for this peripheral in the system spec (`briss-docs/system-spec.md`). Don't invent new ones.

| Pin | Direction | Use |
|---|---|---|
| | | |

## 3. Registers

**This table is the official version.** The game team copies it into `briss_regs.h` by hand, so keep it exact.

| Offset | Name | R/W | Bits | Reset value | Meaning |
|---|---|---|---|---|---|
| 0x00 | | | | | |

## 4. Behaviour

Describe what happens, including timing. For example: "a new position takes effect at the start of the next frame" or "reading BUTTONS clears the PRESSED bits".

## 5. Checks

Each check becomes **exactly one** test in `test/test.py`. Number them so a test can say which check it covers.

- **T1:** after reset, every register reads its reset value.
- **T2:**
- **T3:**

## 6. How the game uses it

A few lines of C showing a typical use. For example:

```c
uint8_t buttons = BRISS_GAMEPAD->buttons;
if (buttons & BTN_LEFT) player_x -= 1;
```

## 7. Versions

| Version | Done when | Target |
|---|---|---|
| v0.1 | Stub: every register exists and reads back; T1 passes | Before Christmas |
| v0.2 | First real behaviour; T1–Tn for that behaviour pass | Mid February |
| v1.0 | Everything in this spec; all checks pass; under size budget | Mid March (design freeze) |

## 8. Open questions

Anything you're not sure about. Tag AND or OR in the pull request to discuss.
