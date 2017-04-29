# Homestead Hard-fork

This is derived
from
[EIP-2](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2.mediawiki). When
this spec is in effect, the following terms should apply.

## Fee Schedule

| Name | Value | Description |
| ---- | ----- | ----------- |
| `G_zero` | 0 | Nothing paid for operations of the set `W_zero` |
| `G_base` | 2 | Amount of gas to pay for operations of the set `W_base`. |
| `G_verylow` | 3 | Amount of gas to pay for operations of the set `W_verylow`. |
| `G_low` | 5 | Amount of gas to pay for operations of the set `W_low`. |
| `G_mid` | 8 | Amount of gas to pay for operations of the set `W_mid`. |
| `G_high` | 10 | Amount of gas to pay for operations of the set `W_high`. |
| `G_ext` | 20 | Amount of gas to pay for operations of the set `W_ext`. |
| `G_sload` | 50 | Paid for a `SLOAD` operation. |
| `G_jumpdest` | 1 | Paid for a `JUMPDEST` operation. |
| `G_sset` | 20000 | Paid for an `SSTORE` operation when the storage value is set to non-zero from zero. |
| `G_sreset` | 5000 | Paid for an `SSTORE` operation when the storage value's zeroness remains unchanged or is set to zero. |
| `R_sclear` | 15000 | Refund given (added into refund counter) when the storage value is set to zero from non-zero. |
| `R_suicide` | 24000 | Refund given (added into refund counter) for suiciding an account. |
| `G_create` | 32000 | Paid for a `CREATE` operation. |
| `G_codedeposit` | 200 | Paid per byte for a `CREATE` operation to succeed in placing code into state. |
| `G_call` | 40 | Paid for a `CALL` operation. |
| `G_callvalue` | 9000 | Paid for a non-zero value transfer as part of the `CALL` operation. |
| `G_callstipend` | 2300 | A stipend for the called contract subtracted from | `G_callvalue` for a non-zero value transfer. |
| `G_callnewaccount` | 25000 | Paid for a `CALL` operation to a not previously excisting account. |
| `G_exp` | 10 | Partial payment for an `EXP` operation. |
| `G_expbyte` | 10 | Partial payment for the `EXP` operation. |
| `G_memory` | 3 | Paid for every additional word when expanding memory. |
| `G_txcreate` | 32000 |  Paid by all contract-creating transactions after the Homestead transition. |
| `G_txdatazero` | 4 | Paid for every zero byte of data or code for a transaction. |
| `G_txdatanonzero` | 68 | Paid for every non-zero byte of data or code for a transaction. |
| `G_transaction` | 21000 | Paid for every transaction. |
| `G_log` | 375 | Partial payment for a `LOG` operation. |
| `G_logdata` | 8 | Paid for each byte in a `LOG` operation's data. |
| `G_logtopic` | 375 | Paid for each topic of a `LOG` operation. |
| `G_sha3` | 30 | Paid for each `SHA3` operation. |
| `G_sha3word` | 6 | Paid for each word (rounded up) for input data to a `SHA3` operation. |
| `G_copy` | 2 | Partial payment for `*COPY` operations, multiplied by words copied, rounded up. |

## Execution

As specified in the yellow paper section 6.2 regarding using `G_txcreate`.

## Signing Transactions

As specified in the yellow paper appendix F regarding signature
validity after Homestead transition.

## Contract Creation

If contract creation does not have enough gas to pay for the final gas
fee for adding the contract code to the state, the contract creation
fails (ie. goes out-of-gas) rather than leaving an empty contract.

## Difficulty Adjustment Algorithm

Change the difficulty adjustment algorithm from the current formula:
<code>block_diff = parent_diff + parent_diff // 2048 * (1 if
block_timestamp - parent_timestamp < 13 else -1) +
int(2**((block.number // 100000) - 2))</code> (where the <code> +
int(2**((block.number // 100000) - 2))</code> represents the
exponential difficulty adjustment component) to <code>block_diff =
parent_diff + parent_diff // 2048 * max(1 - (block_timestamp -
parent_timestamp) // 10, -99) + int(2**((block.number // 100000) -
2))</code>, where <code>//</code> is the integer division operator,
eg. <code>6 // 2 = 3</code>, <code>7 // 2 = 3</code>, <code>8 // 2 =
4</code>. The `minDifficulty` still defines the minimum difficulty
allowed and no adjustment may take it below this.
