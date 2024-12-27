# Kohin SDK

A TypeScript SDK for blockchain and DeFi applications, providing API calls with access key and secret authentication.

## Installation

```bash
npm install kohin-sdk
```

## Environment Setup

Create a `.env` file in your project root:

```env
VITE_RPC_URL="https://polygon-amoy.g.alchemy.com/v2/YOUR_ALCHEMY_KEY"
```

## Quick Start

```typescript
import { Kohin } from 'kohin-sdk';

// Initialize SDK with your credentials
const kohin = new Kohin('<ACCESS_KEY>', '<SECRET_KEY>');
```

## Key Features

### Betting Operations
```typescript
// Get Active Bets
const activeBets = await kohin.getActiveBetData({ userId: '12345' });

// Get Bet Details
const betDetails = await kohin.getBetDetails({ betId: 123 });
```

### Insurance Operations
```typescript
// Calculate Premium
const premium = await kohin.calculatePremium({
  betId: 123,
  betType: "Express",
  odds: 2.5,
  betAmount: 100,
  numLegs: 2,
  maxSubBetLimit: 1000
});

// Buy Cover
const cover = await kohin.buyCover({
  betId: 123,
  betType: "Express",
  slippagePercent: 5,
  coverPremium: 10
});
```

### Liquidity Management
```typescript
// Approve Liquidity
await kohin.approveLiquidity({ amount: 1000 });

// Add Liquidity
await kohin.addLiquidity({ amount: 1000 });

// Remove Liquidity
await kohin.removeLiquidity(depositId, percent);
```

## Prerequisites

- Node.js 14+
- MetaMask or compatible Web3 wallet
- Access to Polygon Amoy network
- Valid API credentials (access key and secret key)

## Network Configuration

The SDK is configured to work with the Polygon Amoy network. Ensure your wallet is connected to:
- Network Name: Polygon Amoy
- Chain ID: 80002
- RPC URL: Your Alchemy RPC URL

## Error Handling

All methods return a response object with this structure:
```typescript
{
  success: boolean;
  data?: T;
  error?: string;
}
```

## Dependencies

- axios: API requests
- ethers: Blockchain interactions
- viem: Web3 utilities
- dotenv: Environment configuration

## Security Notes

- Never commit your `.env` file
- Keep your access key and secret key secure
- Always check transaction details before signing
- Ensure sufficient gas for transactions

## License

MIT License
