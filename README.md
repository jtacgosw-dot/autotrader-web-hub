# AutoTrader Web Hub

Complete React Web Hub for the 3-Sleeve Autonomous Trading System.

## Features

- **5 Pages with Sidebar Navigation:**
  - Overview: System status, performance metrics, quick actions
  - Venues & Latency: Trading venue performance with p95 heatmap
  - Orders & Positions: Trading orders/positions with CSV/JSONL export
  - Risk & Controls: Pause/Resume with 2-step confirmation, bounded sliders
  - Alerts: Alert digest showing state-change notifications

- **Technology Stack:**
  - Vite + React + TypeScript
  - Tailwind CSS + shadcn/ui components
  - React Router for navigation
  - Recharts for data visualization
  - Lucide React for SVG icons

## API Integration

- Base URL: `https://lunaraxolotl.com`
- Authentication: admin/AutoTrader2025!
- Endpoints: `/api/health`, `/api/pause`, `/api/resume`, `/api/risk`, `/api/venues/health`, `/api/orders`, `/api/positions`

## Deployment

Multi-stage Docker build with static nginx serving:

```bash
# On EC2 instance
cd /home/ubuntu/autotrader
git pull
docker compose build --no-cache web nginx
docker compose up -d --remove-orphans
```

## Export Formats

**CSV (Orders):**
```
time_iso,pair,side,size,entry_price,current_price,fees_usd,slippage_bps,latency_ms,venue,pnl_realized_usd,order_id,trade_id
```

**JSONL (Orders):**
```json
{"ts":"2025-08-19T14:22:05Z","pair":"ETH/USDT","side":"BUY","qty":1.20,"price":1987.50,"notional_usd":2385.00,"fee_usd":2.38,"slippage_bps":3.2,"latency_ms":287,"venue":"Binance","pnl_realized_usd":-5.20,"order_id":"o_9q3g5","trade_id":"t_44b1a"}
```

## Development

```bash
npm install
npm run dev
npm run build
```

## Link to Devin run
https://app.devin.ai/sessions/a91172236130494b99e7508396c42797

Requested by: @Vac1234
