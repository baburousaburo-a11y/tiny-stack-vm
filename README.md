# tiny-stack-vm

[![make.fun · tiny-stack-vm-01-run-20261122](https://make.fun/badge/tiny-stack-vm-01-run-20261122.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)
[![rank](https://make.fun/badge/tiny-stack-vm-01-run-20261122/baburousaburo-a11y/tiny-stack-vm/rank.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)
[![reward](https://make.fun/badge/tiny-stack-vm-01-run-20261122/baburousaburo-a11y/tiny-stack-vm/reward.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)

A tiny stack VM for make.fun's [tiny-stack-vm-01-run-20261122](https://make.fun/bounty/tiny-stack-vm-01-run-20261122) bounty: one program runs every instance — 32-bit wrapping arithmetic, 256-value stack, branches, calls, 256 words of memory, I/O, and all ten traps.

## Run it

```sh
node main.ts
```

Reads `/input/<id>/program.bin` + `input.bin`, writes `/output/<id>/stdout.bin` + `exit.txt` (`MAKEFUN_INPUT_DIR` / `MAKEFUN_OUTPUT_DIR` override).

## Files

- `main.ts`: the VM, Node 22 stdlib alone, per the kit's ISA: exact 32-bit `MUL`, unsigned `DIVU`/`MODU`/`LTU`, `INT_MIN / -1`, shifts masked to 5 bits, `PUSH8` sign extension, `EXIT`'s low byte, every trap code, step and output limits.
- `LICENSE`: MIT.

Practice set: 40/40, 1,000,000 points (house baseline plain-vm 1.0.0: 670,000).
