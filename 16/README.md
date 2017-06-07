---
domain: rfc.ethereumclassic.org
shortname: 16/EVMJSON
name: EVM JSON-RPC
status: raw
editor: Wei Tang <hi@that.world>
---

## Overview

JSON-RPC is a stateless, lightweight remote procedure call (RPC)
protocol. This specification describes the JSON-RPC API that should be
provided by an EVM implementation.

## Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in RFC 2119.

## Endpoint

An EVM that supports JSON-RPC MUST provide an endpoint for calling.

## Hex Value Encoding

Bytearrays are transferred using hex value encoding. The string MAY
optionally start with "0x" followed by 0-9a-f. The string MUST be even
number of digits.

As a result, several hex value encodings that are considered wrong in
Ethereum JSON-RPC ("0x", for example, in this specification represents
an empty bytearray) would have no problem in EVM JSON-RPC.

## Methods

### `evm_create`

Creates a new VM using the given block header and context. It returns
an ID that represents this VM.

#### Parameters

1. `BlockHeader` struct: contains the block header information.
2. `Context` struct: contains the current execution context.
3. `Patch`: a unique number that represents the current patch version of
   the block.

##### `BlockHeader` Fields

* `coinbase`: 20 bytes address.
* `timestamp`: 32 bytes.
* `number`: 32 bytes.
* `difficulty`: 32 bytes.
* `gas_limit`: 32 bytes gas.

##### `Context` Fields

* `address`: 20 bytes address.
* `caller`: 20 bytes address.
* `code`: bytearray for the code to run.
* `data`: bytearray for the data to be passed. Should be empty when
  the transaction is contract creation.
* `gas_limit`: 32 bytes.
* `gas_price`: 32 bytes.
* `origin`: 20 bytes address. Usually the same as `caller`.
* `value`: ether to be passed in this transaction. The client is
  responsible to make sure that the caller has enough balance to pay.

#### Returns

An integer that represents the current VM.

### `evm_fire`

Fire an existing VM.

#### Parameters

1. `evm_id`: an integer that is the VM id.

#### Returns

Either `"ok"`, `{"requireAccount": "{address}"}`,
`{"requireAccountCode": "{address}"}` or `{"requireBlockhash":
"{number}"}`.

### `evm_commit_account`

Commit an account into the VM. The client is then not supposed to
modify the account if it wants to accept the result of the VM later.

#### Parameters

1. `evm_id`: an integer that is the VM id.
2. `address`: 20 bytes address.
3. `Account` struct: contains the full account information.

##### `Account` fields

* `nonce`: 32 bytes.
* `balance`: 32 bytes.
* `storage`: a struct, where the key is a non-zero-value index, and
  the value is the corresponding value in the storage.
* `code`: bytearray for the code in the account.

#### Returns

Either `"ok"` or `{"error": "{message}"}`.

### `evm_commit_account_code`

Commit the code of an account into the VM.

#### Parameters

1. `evm_id`: an integer that is the VM id.
2. `address`: 20 bytes address.
3. `code`: bytearray for the code in the account.

#### Returns

Either `"ok"` or `{"error": "{message}"}`.

### `evm_commit_blockhash`

Commit a blockhash into the VM.

#### Parameters

1. `evm_id`: an integer that is the VM id.
2. `number`: 32 bytes.
3. `hash`: 32 bytes.

#### Returns

Either `"ok"` or `{"error": "{message}"}`.

### `evm_accounts`

Returns the current account status in the VM.

#### Parameters

1. `evm_id`: an integer that is the VM id.

#### Returns

A struct.

* `fulls`: a struct where key is an address, and value is an `Account`
  struct.
* `increases`: balances to increase for accounts. Key is an address,
  and value is the balance to be increased.

### `evm_appending_logs`

Returns the logs to be appended if the client decides to accept the
VM's result.

#### Parameters

1. `evm_id`: an integer that is the VM id.

#### Returns

An ordered array, where values are `Log` structs.

##### `Log` Fields

* `address`: 20 bytes address.
* `data`: bytearray for the data of the log.
* `topics`: array of 32 bytes.

### `evm_out`

Returns the out value of the VM execution result.

#### Parameters

1. `evm_id`: an integer that is the VM id.

#### Returns

A bytearray that is the out value of the VM.
