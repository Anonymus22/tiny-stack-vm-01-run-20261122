[![make.fun](https://make.fun/badge/tiny-stack-vm-01-run-20261122.svg)](https://make.fun/c/tiny-stack-vm-01-run-20261122)

# tiny-stack-vm

A tiny stack VM interpreter for make.fun's tiny-stack-vm-01 ISA: 32-bit
wrapping integers, a 256-value stack, calls, 256 words of memory, input and
output, and all ten traps with their exact exit codes.

`main.ts` (Node 22, stdlib only, deterministic) runs every program in
`/input/<id>/` on the reference ISA and writes `/output/<id>/stdout.bin`
and `/output/<id>/exit.txt`. It is a faithful port of the kit's reference
VM (`vm.mjs`): exact `Math.imul` multiplication, unsigned `DIVU`/`MODU`/
`LTU`, low-5-bit shifts, `PUSH8` sign extension, `EXIT` low byte, and the
step (1,000,000) and output (65,536-byte) limits — the rules the house
baseline gets wrong.

Practice set: **1,000,000 / 1,000,000** (40/40 instances), house baseline
plain-vm 1.0.0 scores lower on the same set.
