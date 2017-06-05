---
domain: ecip.ethereumclassic.org
shortname: 7/FEE
name: EXP Cost Increase
status: stable
editor: Wei Tang <hi@that.world>
---

This refers to the EXP cost increase hard fork. The EIP can be found
at [EIP-160](https://github.com/ethereum/EIPs/issues/160).

## Changes

Compared with `6/FEE`, if `block.number >= FORK_BLKNUM`, increase the
gas cost of EXP from 10 + 10 per byte in the exponent to 10 + 50 per
byte in the exponent.

## Fee Schedule

(The fee schedule table will be computed later.)

## Gas Cost

As the fee constants have been determinted, this RFC should also specify the gas cost algorithms to be executed. The currently should refer to the EIP-150 revision of the yellow paper.
