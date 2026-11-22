## What this changes

<!-- One or two sentences. -->

Closes #

## Checklist

- [ ] The tests pass on my laptop (`cd test && make`)
- [ ] I only built registers that are in `SPEC.md`
- [ ] Any new behaviour has a test, written by someone other than me
- [ ] No new lint warnings
- [ ] If registers changed: `SPEC.md` **and** the game's `briss_regs.h` are both updated (needs a `spec-change` issue after the freeze)

## Reviewer checklist

- [ ] The code matches `SPEC.md`
- [ ] The register table in `SPEC.md` matches `briss_regs.h` in briss-game
- [ ] The tests actually check the behaviour (not just that it runs)
