# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Crypto Dash is a React-based cryptocurrency dashboard that displays real-time market data from the CoinGecko API. Users can browse top cryptocurrencies, filter/sort them, and view detailed information with price charts.

## Commands

- `npm run dev` - Start development server with HMR
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

## Architecture

**Tech Stack:** React 19, Vite 7, React Router 7, Chart.js with react-chartjs-2

**Routing Structure (defined in `src/App.jsx`):**
- `/` - Home page with coin list
- `/about` - About page
- `/coin/:id` - Coin details with price chart
- `*` - 404 page

**Data Flow:**
- `App.jsx` fetches coin list data and manages global state (coins, filter, sort, limit)
- State is passed down to `HomePage` which handles filtering/sorting logic client-side
- `CoinDetailsPage` fetches individual coin data independently using the `:id` route param
- `CoinChart` fetches 7-day price history for the chart

**API Configuration:**
- Environment variables in `.env`:
  - `VITE_COINS_API_URL` - CoinGecko markets endpoint (for coin list)
  - `VITE_COIN_API_URL` - CoinGecko coins endpoint (for details/charts)

**Key Components:**
- `components/CoinCard.jsx` - Displays coin summary, links to details page
- `components/CoinChart.jsx` - Line chart using Chart.js with time scale (requires chartjs-adapter-date-fns)
- `components/FilterInput.jsx`, `LimitSelector.jsx`, `SortSelector.jsx` - Control components for list filtering

## ESLint Configuration

Uses flat config format (`eslint.config.js`) with:
- React Hooks plugin (recommended rules)
- React Refresh plugin (Vite configuration)
- Custom rule: `no-unused-vars` ignores variables starting with uppercase letters or underscores
