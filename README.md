# Kohin SDK

A TypeScript SDK for interacting with Kohin's insurance protocol on the Polygon network. This SDK provides methods for managing insurance covers, liquidity operations, and retrieving betting information.

## Installation

```bash
npm install kohin-sdk bash```


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

// Import the required modules
import { add } from './utils';

// Define a function
const greet = (name: string): string => {
  return `Hello, ${name}!`;
};

typescript
// Call the function
console.log(greet("Chintan"));

// Perform a calculation
const result = add(2, 3);
console.log(`The result is: ${result}`);

