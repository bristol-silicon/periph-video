![](../../workflows/test/badge.svg)

# Video

**Team:** XOR · **Sub-group:** VGA timing · Sprite · Text overlay · **Owners:** TBD (two names, added at the first session)

Part of the **Bristol Silicon Society (BriSS)** RISC-V games chip: TinyQV plus our own peripherals, taped out on the Tiny Tapeout GF180 shuttle.

- 📄 **Spec:** [SPEC.md](SPEC.md). Read this first.
- 🤝 **How to contribute:** [CONTRIBUTING.md](CONTRIBUTING.md)
- 🗺️ **The whole chip:** [briss-docs](https://github.com/bristol-silicon/briss-docs)

## What's in this repo

| Path | What it is |
|---|---|
| `src/peripheral.v` | Your peripheral's Verilog (module `tqvp_briss_video`) |
| `src/tt_wrapper.v` | Connects your peripheral to the test harness |
| `test/test.py` | Automated tests (cocotb). One test per check in `SPEC.md` |
| `docs/info.md` | Datasheet text for Tiny Tapeout |
| `SPEC.md` | Our spec: registers, behaviour, checks |

## Running the tests on your laptop

You need Python 3.11+ and Icarus Verilog.

```bash
pip install -r test/requirements.txt
cd test
make
```

The same tests run automatically on GitHub every time you push. Look for the green tick (or red cross) next to your commit.

## Where this came from

This repo is based on Tiny Tapeout's [TinyQV full peripheral template](https://github.com/TinyTapeout/tinyqv-full-peripheral-template) (Apache-2.0). Thanks to Tiny Tapeout for the template, and for sponsoring two of our tiles.
