# min-rvwmo-litmus-tests

This minimal testsuite is an adaptation of the 39 tests found in this paper:
https://www.cl.cam.ac.uk/~pes20/ppc-supplemental/test6.pdf

This collection of litmus tests aims to provide coverage of the majority
of the behavior allowed/disallowed by the RVWMO memory model. For complete
coverage, please refer to the [RISC-V Litmus Tests repo](https://github.com/litmus-tests/litmus-tests-riscv).

# Test creation
Most tests were generated using diy7. Files in the /conf directory that
end with -ext generate more than just the described test.

Tests may have been edited from the generated file to better
match the exists() clause from the paper.

Handwritten tests have a note at the top saying such.

If you want to run diy7 to generate the tests associated with a conf
file, use a command like this:
`diy7 -arch RISCV -conf conf/2+2W.conf`

# TODO:
Verify lwsync/sync->RISCV fence translation correctness
[ ] PPO000-019
[ ] ISA2
[ ] PPOAA
[ ] PPOCA
[ ] RDW
[ ] RSW
[ ] MP+sync+rs
[ ] MP+nondep+sync

# Running against the axiomatic model
`herd7 -model riscv.cat tests\@all`
