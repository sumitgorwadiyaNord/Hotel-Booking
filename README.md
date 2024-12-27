# Kohin SDK

**Version:** 1.0.0  
A TypeScript SDK for API calls with access key and secret authentication, designed for blockchain and DeFi applications.

## Features

- Provides APIs for managing active bets, bet details, and odd history.
- Facilitates insurance operations like premium calculation, buying cover, and adding liquidity.
- Includes support for interaction with smart contracts using the Polygon network.

## Installation

Install the SDK via npm:

```bash
npm install kohin-sdk
```

Usage
Importing the SDK
Import the Kohin class from the SDK to begin using it.

typescript
Copy code
import { Kohin } from 'kohin-sdk';
Initialization
Create an instance of the Kohin class by providing your access key and secret key.

typescript
const kohin = new Kohin('<ACCESS_KEY>', '<SECRET_KEY>');

Example: Fetching Active Bets
typescript
Copy code
const params = { userId: '12345' }; // Example parameters
try {
const activeBets = await kohin.getActiveBetData(params);
console.log('Active Bets:', activeBets);
} catch (error) {
console.error('Error fetching active bets:', error);
}
API Reference
Methods

1. getActiveBetData(params: ActiveBetParams): Promise<ResponseData<Bet[]>>
   Fetches active bet data for a user.

2. getBetDetails(params: BetDetailsParams): Promise<ResponseData<BetDetails>>
   Fetches details of a specific bet.

3. getOddsHistory(params: OddHistoryParams): Promise<ResponseData<OddsHistory[]>>
   Retrieves odds history.

4. buyCover(params: BuyCoverParams): Promise<BuyCoverResponse>
   Buys insurance cover for a bet.

5. calculatePremium(params: CalculatePremiumParams): Promise<CalculatePremiumResponse>
   Calculates the premium for an insurance cover.

6. addLiquidity(params: AddLiquidityParams): Promise<AddLiquidityResponse>
   Adds liquidity to the insurance pool.

Utilities
hasCoverBooked: Checks if a cover is already booked.
getComboBetLimits: Retrieves minimum and maximum limits for combo bets.
getMinDeposit: Fetches the minimum deposit amount.
Smart Contract Integration
The SDK uses smart contracts deployed on the Polygon network. Ensure you have a wallet connected and sufficient gas for transactions.

Required Dependencies
The following libraries are required for using this SDK:

axios
ethers
dotenv
These will be installed automatically with the SDK.

Development
To build the SDK locally:

bash
Copy code
npm run build
To test the SDK:

bash
Copy code
npm run test
License
This project is licensed under the MIT License. See the LICENSE file for details.
