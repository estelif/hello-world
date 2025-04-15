# Solana Rust Program Development

This repository contains a simple "Hello World" example for Solana program development using Rust, based on the official [Solana documentation](https://solana.com/ru/docs/programs/rust).

## Prerequisites

Before getting started, ensure you have:
- Solana CLI installed
- Rust toolchain installed
- Basic understanding of Solana blockchain concepts

### Create a New Project
```bash
cargo new hello_world --lib
cd hello_world
```

## Program Structure

A basic Solana program includes:

1. **Cargo.toml** with required dependencies:
```toml
[lib]
crate-type = ["cdylib", "lib"]

[dependencies]
solana-program = "1.8.0"
```

2. **lib.rs** - Main program file:
```rust
use solana_program::{
    account_info::AccountInfo,
    entrypoint,
    entrypoint::ProgramResult,
    pubkey::Pubkey,
};

entrypoint!(process_instruction);

pub fn process_instruction(
    program_id: &Pubkey,
    accounts: &[AccountInfo],
    instruction_data: &[u8],
) -> ProgramResult {
    // Program logic here
    Ok(())
}
```

## Key Concepts

1. **Entrypoint**: The main function that processes all instructions
2. **Accounts**: All data is stored in accounts that programs can read/write
3. **Instructions**: Commands that tell the program what operation to perform
4. **Program-derived Addresses (PDAs)**: Special addresses that only the program can sign for

## Development Workflow

1. **Build the program**:
```bash
cargo build-bpf
```

2. **Deploy to local cluster**:
```bash
solana program deploy ./target/deploy/hello_world.so
```

3. **Interact with the program** using client code
## Getting Started

1. Clone this repository
2. Build the program:
   ```bash
   cargo build-bpf
   ```

## Deployment

To deploy the program to the Solana blockchain:

```bash
solana program deploy ./target/deploy/hello_world.so
```

Example output:
```
Program Id: C2FBTySszdtZBaekLTfw6R8Z6WPkdQKusYxtE3DCaFQ2
Signature: SnjHnjTkBMAcy3W4rNqaNvt8pq28f9BySY2AAv5ar6QbUf5WYDYkAB2eJg6Jz4uBs3M5oAMhBYEqfGaia6njGL7Z
```
![image](https://github.com/user-attachments/assets/80822dd8-afea-4b37-989b-44b50cbc6084)

## Funding Account

Before interacting with the program, ensure your account has sufficient SOL:

```bash
solana address  # Check your address
solana airdrop 1  # Request 1 SOL
solana airdrop 2  # Request additional SOL if needed
```
![image](https://github.com/user-attachments/assets/74413d16-e8ce-4a68-b55a-47e3c8d5b6af)


