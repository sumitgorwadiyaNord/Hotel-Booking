# Kohin SDK

A TypeScript SDK for interacting with Kohin's insurance protocol on the Polygon network. This SDK provides methods for managing insurance covers, liquidity operations, and retrieving betting information.

## Installation

```npm install kohin-sdk```


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
