# MyToken (MTK)

## Overview
MyToken is a simple ERC-20 compatible token built on Ethereum for learning purposes.

## Token Details
- Name: MyToken
- Symbol: MTK
- Decimals: 18
- Total Supply: 1,000,000 MTK

## What is ERC-20?
ERC-20 is an Ethereum token standard that defines common functions all tokens should implement.

## Features
- Standard ERC-20 functions: balanceOf, transfer, approve, transferFrom, allowance
- Fixed total supply minted to deployer
- Transfer and delegated transfer via transferFrom
- Transfer and Approval events
- Input validation for zero addresses and balances

## Contract Location
- File: contracts/MyToken.sol
- Solidity: ^0.8.0 or higher

## How to Deploy with Remix

1. Open https://remix.ethereum.org/
2. Create contracts/MyToken.sol
3. Paste the contract code
4. Compile with Solidity 0.8.x
5. Deploy:
   - Environment: JavaScript VM
   - Constructor: 1000000000000000000000000 (1 million tokens)
6. Verify contract address under Deployed Contracts

## How to Use

### Check Balance
balanceOf(address account) - Returns token balance

### Transfer Tokens
transfer(address to, uint256 amount) - Transfer tokens to an address

### Approve Spending
approve(address spender, uint256 amount) - Allow spender to use tokens

### Transfer on Behalf
transferFrom(address from, address to, uint256 amount) - Transfer using allowance

### Check Allowance
allowance(address owner, address spender) - Check remaining approval

## Testing Scenarios

- After deployment: balanceOf shows total supply
- Transfer test: Balances update, Transfer event emitted
- Approve test: Allowance set, Approval event emitted
- TransferFrom: Balances and allowance update correctly
- Edge cases:
  - Transfer to address(0) reverts
  - Insufficient balance reverts
  - Insufficient allowance reverts

## Why 18 Decimals?

Following Ethereum standard, 1 token = 10^18 smallest units. This allows fractional amounts and compatibility with wallets and exchanges.

## Transfer vs TransferFrom

- transfer: Moves your own tokens to another address
- transferFrom: Allows approved third party to move tokens between addresses

## Contract Security

- Input validation: Zero address and balance checks
- Allowance mechanism: Prevents unauthorized spending
- Event emission: Logs all transfers and approvals
- Solidity 0.8.x: Built-in overflow/underflow protection
- Clear error messages with require statements

## What I Learned

- ERC-20 standard defines common token interface
- Balances and allowances use Solidity mappings
- Events enable wallets to track token activity
- Input validation is crucial for security
- Remix IDE for contract development and testing
- Decimals make tokens compatible with wallets
- Constructor initializes supply and mints to deployer

## License

MIT License
