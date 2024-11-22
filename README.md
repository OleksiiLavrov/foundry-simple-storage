## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Setup

### Install Foundry:

```shell
curl -L https://foundry.paradigm.xyz | bash
```

### Run Foundryup:

```shell
foundryup
```

### Setup dev environment:

#### Run anvil:

```shell
anvil
```

#### Choose one of private keys provided by anvil and run cast wallet import:

```shell
cast wallet import <KEY_NAME> --interactive
```
By doing this you encrypt the private key and store it in the keystore.

## Usage

### Build

```shell
forge build
```

### Test

```shell
forge test
```

### Format

```shell
forge fmt
```

### Gas Snapshots

```shell
forge snapshot
```

### Anvil

```shell
anvil
```

### Deploy

```shell
forge script <SCRIPT_NAME> --broadcast --rpc-url <RPC_URL> --account <KEY_NAME> --sender <SENDER_ADDRESS>
```
Example:
```shell
forge script DeploySimpleStorage.s.sol:DeploySimpleStorage --broadcast --rpc-url http://127.0.0.1:8545 --account 0xac0974bec39a17e36ba4a6b4d210ff944bacb478cbed5efcae784d7bf4f2ss22 --sender 0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266
```

### Cast

```shell
cast <subcommand>
```

### Help

```shell
forge --help
anvil --help
cast --help
```

## Useful tips

- Use `cast --to-base <HASH> dec` in the terminal to convert a hash to decimal.
- Use `cast wallet import <KEY_NAME> --interactive` to store private keys in the keystore. Remember the password that was set.
  To run scripts with stored private keys, use 
  `forge script <SCRIPT_NAME> --broadcast --rpc-url <RPC_URL> --account <KEY_NAME> --sender <SENDER_ADDRESS (WALLET_ADDRESS)>`.
- Use `cast wallet list` to list the wallets in the keystore.
- Use `cast <CAST_METHOD> <CONTRACT_ADDRESS> "<FUNCTION_NAME>(<ARGUMENTS_TYPE>)" <ARGUMENTS> --rpc-url <RPC_URL> --keystore ~/.foundry/keystores/<KEY_NAME>`
  to make a transaction to / call a method of a contract with encrypted private key.
