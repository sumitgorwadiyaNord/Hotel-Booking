# Kohin SDK

A TypeScript SDK for blockchain and DeFi applications, providing API calls with access key and secret authentication.

## Installation

```bash
npm install kohin-sdk
```

## Quick Start

```typescript
import { Kohin } from 'kohin-sdk';

// Initialize SDK with your credentials
const kohin = new Kohin('<ACCESS_KEY>', '<SECRET_KEY>');
```

## Core Features

### Betting Operations
```typescript
// Get Active Bets
const activeBets = await kohin.getActiveBetData({ userId: '12345' });

// Get Bet Details
const betDetails = await kohin.getBetDetails({ betId: 123 });

// Get Odds History
const oddsHistory = await kohin.getOddsHistory({ eventId: 456 });
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

// Add Liquidity
const liquidity = await kohin.addLiquidity({ amount: 1000 });
```

### Utility Functions
```typescript
// Check if cover is booked
const coverStatus = await kohin.hasCoverBooked({ betId: 123 });

// Get combo bet limits
const limits = await kohin.getComboBetLimits();

// Get minimum deposit
const minDeposit = await kohin.getMinDeposit();
```

## Important Notes

- Ensure you have a valid access key and secret key
- The SDK uses the Polygon network for smart contract interactions
- Sufficient gas is required for blockchain transactions
- All amounts are in the native token units

## Requirements

- Node.js 14+
- Web3 wallet for blockchain interactions
- Polygon network connection

## Dependencies

- axios
- ethers
- viem
- dotenv

## Error Handling

All methods return a response object with the following structure:
```typescript
{
  success: boolean;
  data?: T;
  error?: string;
}
```

## License

MIT License
