---
domain: ecip.ethereumclassic.org
shortname: 6/REPLAY
name: Signing Transactions with Simple Replay Attach Protection
status: stable
editor: Wei Tang <hi@that.world>
---

This refers to the replay attack protection hard fork. The EIP can be
found at [EIP-155](https://github.com/ethereum/EIPs/issues/155).

## Changes

Compared with `15/TRASIG`, if `block.number >= FORK_BLKNUM` and `v =
CHAIN_ID * 2 + 35` or `v = CHAIN_ID * 2 + 36`, then when computing the
hash of a transaction for purposes of signing or recovering, instead
of hashing only the first six elements (ie. nonce, gasprice, startgas,
to, value, data), hash nine elements, with v replaced by CHAIN_ID, r =
0 and s = 0. The currently existing signature scheme using v = 27 and
v = 28 remains valid and continues to operate under the same rules as
it does now.
