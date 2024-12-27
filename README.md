# Kohin SDK

A TypeScript SDK for blockchain betting and insurance operations on the Polygon network.

## Installation

```bash
npm install kohin-sdk
```

## Requirements

- Node.js 14+
- Web3 Wallet (MetaMask)
- Access Key and Secret Key
- Polygon Network RPC URL

## Environment Configuration

Create a `.env` file:

```env
VITE_ENV_MODE="test" # "test", "preprod", or "prod"
VITE_RPC_URL="https://polygon-amoy.g.alchemy.com/v2/YOUR_KEY"
```

## Network Support

- Test: Polygon Amoy (Chain ID: 80002)
- Production: Polygon Mainnet

## Quick Start

```typescript
import { Kohin } from "kohin-sdk";

// Initialize SDK with credentials
const kohin = new Kohin("<ACCESS_KEY>", "<SECRET_KEY>");
```

## Core Features

### Betting Operations

```typescript
// Get Active Bets
const activeBets = await kohin.getActiveBetData({
  bettorAddress: "0x...",
  pageCount: 1,
});

// Get Bet Details
const details = await kohin.getBetDetails({
  betId: "0x...",
});

// Get Odds History
const history = await kohin.getOddsHistory({
  conditionId: "0x...",
});
```

### Insurance Operations

```typescript
// Calculate Premium
const premium = await kohin.calculatePremium({
  betId: 123,
  betType: "Express", // or "Ordinar"
  odds: 2.5,
  betAmount: 100,
  numLegs: 2,
  maxSubBetLimit: 1000,
});

// Buy Cover
const cover = await kohin.buyCover({
  betId: 123,
  betType: "Express",
  slippagePercent: 5,
  coverPremium: BigInt(1000000), // 1 USDT (6 decimals)
});
```

### Liquidity Management

```typescript
// Add Liquidity
await kohin.approveLiquidity({ amount: 1000 });
const deposit = await kohin.addLiquidity({ amount: 1000 });

// Remove Liquidity
const withdrawal = await kohin.removeLiquidity(depositId, 100); // 100%
```

## Response Types

All methods return a consistent response format:

```typescript
interface ResponseData<T> {
  success: boolean;
  data?: T;
  error?: string;
}
```

## Error Handling

```typescript
try {
  const result = await kohin.someOperation(params);
  if (result.success) {
    // Handle success
  } else {
    // Handle error
  }
} catch (error) {
  // Handle unexpected errors
}
```

## Dependencies

- viem: Web3 interactions
- axios: API requests
- typescript: Type definitions

## Security Best Practices

- Store credentials securely
- Never commit `.env` files
- Validate all transaction parameters
- Maintain sufficient gas for transactions
- Check MLR (Maximum Loss Ratio) before operations

## License

MIT
