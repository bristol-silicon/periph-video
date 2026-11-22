# Peripheral spec: <NAME>

> Copy this file, fill in every section, and open a pull request.
> Your team's game team (AND) and integration team (OR) must approve it **before** you write any Verilog.
> After the December spec freeze, changes need a `spec-change` issue (see CONTRIBUTING.md).

| | |
|---|---|
| **Team / sub-group** | e.g. NOR / Gamepad reader |
| **Owners** (2 names) | |
| **Type** | Full peripheral (≤ 2 tiles) or byte peripheral (≤ 1 tile) |
| **Slot number** | Given by OR |
| **Size budget** | Given by OR, in cells |
| **Status** | Draft / Approved / Frozen |

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
