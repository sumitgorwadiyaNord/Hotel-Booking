# Kohin SDK

A TypeScript SDK for interacting with Kohin's insurance protocol on the Polygon network. This SDK provides methods for managing insurance covers, liquidity operations, and retrieving betting information.

## Installation
```bash
npm install kohin-sdk


## Configuration

To use the SDK, you'll need:
- Access Key and Secret Key from Kohin
- A Web3 provider (the SDK is configured to work with Polygon Amoy testnet)

## Basic Usage
import { Kohin } from 'kohin-sdk';
// Initialize the SDK with your credentials
const kohin = new Kohin('YOUR_ACCESS_KEY', 'YOUR_SECRET_KEY');



## Core Features

### Betting Information
// Get Active Bets
const activeBets = await kohin.getActiveBetData({
page: 1,
limit: 10
});
// Get Bet Details
const betDetails = await kohin.getBetDetails({
betId: 123
});
// Get Odds History
const oddsHistory = await kohin.getOddsHistory({
betId: 123
});



### Insurance Operations

⌘K to generate a command
Can you prepare readMe file, brief about how to use SDK?

I'll help you create a comprehensive README.md file for the Kohin SDK. Here's a well-structured documentation:
bash
npm install kohin-sdk
import { Kohin } from 'kohin-sdk';
// Initialize the SDK with your credentials
const kohin = new Kohin('YOUR_ACCESS_KEY', 'YOUR_SECRET_KEY');

// Get Active Bets
const activeBets = await kohin.getActiveBetData({
page: 1,
limit: 10
});
// Get Bet Details
const betDetails = await kohin.getBetDetails({
betId: 123
});
// Get Odds History
const oddsHistory = await kohin.getOddsHistory({
betId: 123
});
// Calculate Premium
const premium = await kohin.calculatePremium({
betId: 123,
betType: "Express", // or "Ordinar"
odds: 2.5,
betAmount: 100,
numLegs: 1,
maxSubBetLimit: 1000
});
// Buy Cover
const cover = await kohin.buyCover({
betId: 123,
betType: "Express",
slippagePercent: 5,
coverPremium: premium.calculatedPremium
});
// Settle Claim
const settlement = await kohin.settleClaim({
coverId: 456
});



### Liquidity Management
// Add Liquidity
// First approve the token spending
await kohin.approveLiquidity({ amount: 1000 });
// Then add liquidity
const addLiquidity = await kohin.addLiquidity({
amount: 1000
});
// Remove Liquidity
const removeLiquidity = await kohin.removeLiquidity(
depositId: 789,
percent: 100 // Remove 100%
);



### Utility Functions
// Check if a bet has cover
const coverStatus = await kohin.hasCoverBooked({ betId: 123 });
// Get token balance
const balance = await kohin.getTokenBalance();
// Get pool limits
const minDeposit = await kohin.getMinDeposit();
const maxDeposit = await kohin.getMaxDeposit();
const maxPoolCap = await kohin.getMaxPoolCap();


## Transaction History

// Get My Slips
const mySlips = await kohin.getMySlips({
page: 1,
limit: 10
});
// Get Slip History
const slipHistory = await kohin.getSlipHistory({
page: 1,
limit: 10
});
// Get Transaction History
const txHistory = await kohin.getTransactionHistory({
page: 1,
limit: 10
});
// Get My Deposits
const deposits = await kohin.getMyDeposits({
page: 1,
limit: 10
});





## Error Handling

The SDK includes comprehensive error handling. All methods return a response object with the following structure:

success: boolean;
data?: T;
error?: string;
}




## Dependencies

- viem: For blockchain interactions
- axios: For API calls
- typescript: For type safety

## Network Support

Currently supports:
- Polygon Amoy Testnet

## License

MIT

## Support

For support, please contact [Kohin support team](https://kohin.io)



