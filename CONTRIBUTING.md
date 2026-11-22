# How we work

This is the BriSS way of making changes. It's the same in every peripheral repo.

## The golden rules

1. **Never push straight to `main`.** Every change goes on a branch and becomes a pull request (PR).
2. **Every PR needs green checks and one review** before it merges.
3. **Whoever writes a feature's Verilog doesn't write its test.** Swap within your sub-group.
4. **The spec comes first.** Don't build a register that isn't in `SPEC.md`.

## Making a change, step by step

```bash
git clone https://github.com/bristol-silicon/<repo>.git   # once
cd <repo>
git switch main && git pull                              # get the latest
git switch -c yourname/short-description                 # new branch
# ... edit files ...
cd test && make && cd ..                                 # run the tests locally
git add -A
git commit -m "Add BUTTONS register reset value"
git push -u origin yourname/short-description
```

Then open the link Git prints, or go to the repo on GitHub and click **Compare & pull request**.

## Pull requests

- Keep them small: one feature or one fix. A PR should take a reviewer 10 minutes, not an hour.
- Fill in the checklist in the PR description.
- Link the issue it closes: write `Closes #12` in the description.
- If the checks go red, click **Details** to see why, fix it, and push again to the same branch.

## Tasks

- Every task is a GitHub **issue**, small enough to finish in one session, with a "Done when…" line.
- Assign yourself before you start, so no one else picks it up.
- Stuck for more than 20 minutes? Comment on the issue or ask in your team's WhatsApp group.

## Changing the spec after the freeze

From mid-December the register table is frozen. To change it:

1. Open an issue using the **Spec change** template.
2. It needs approval from: one owner of this peripheral, one person from AND (game) and one from OR (integration).
3. The PR that makes the change must update **both** `SPEC.md` and the game's `briss_regs.h`.

## Versions

When a version is done (v0.1, v0.2, v1.0), ask OR to tag it. Only OR changes which version goes into the chip.

## Style

Follow the coding guide in [briss-docs](https://github.com/bristol-silicon/briss-docs/blob/main/coding-guide.md). In short: one clock, the template's reset, no latches, and no warnings.
