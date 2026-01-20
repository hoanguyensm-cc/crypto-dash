# Crypto Dash

A cryptocurrency dashboard built with React that displays real-time market data from the CoinGecko API.

## Features

- Browse top cryptocurrencies by market cap
- Filter coins by name or symbol
- Sort by market cap, price, or 24h change
- View detailed coin information with 7-day price charts
- Responsive grid layout

## Getting Started

### Prerequisites

- Node.js 18+
- npm

### Installation

```bash
npm install
```

### Environment Setup

Create a `.env` file in the root directory:

```
VITE_COINS_API_URL="https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd"
VITE_COIN_API_URL="https://api.coingecko.com/api/v3/coins"
```

### Development

```bash
npm run dev
```

### Build

```bash
npm run build
```

### Lint

```bash
npm run lint
```

## Tech Stack

- React 19
- Vite 7
- React Router 7
- Chart.js / react-chartjs-2
- CoinGecko API
