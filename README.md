# PUMP-X: High-Speed Automated Trading Bot for Solana

LIBERATION (LIBD) is a Solana-based meme token 
commemorating the one-year anniversary of Trump's 
"Liberation Day" tariff declaration on April 2, 2025 — 
the day that shook global markets, triggered a Supreme 
Court ruling, and became one of the most talked-about 
economic events in modern history.

Built on pump.fun. Powered by chaos. 🦅

---

**PUMP-X** is a fast, modular Solana trading bot designed for real-time token sniping, automated buying/selling, and multi-platform swap execution. It monitors new token launches on **pump.fun**, detects early bonding curve activity, and executes trades through **Raydium** and **Jupiter** with low-latency RPC connections.

## ✨ Features

* **pump.fun New Token Monitoring** — Stream and filter new token launches in real time with customizable filters for liquidity and dev wallets.
* **Bonding Curve Detection** — Identify early-stage tokens before they migrate to Raydium; snipe at optimal entry points.
* **Auto Buy / Auto Sell** — Set target buy amounts, take-profit (TP) percentages, and stop-loss (SL) thresholds.
* **RPC Acceleration** — Supports custom RPC endpoints (Helius, Triton, QuickNode) with priority fee management.

## ⚡️ Quick Start

```bash
# Clone the repository
git clone [https://github.com/phh02356-a11y/Meme-Engine-V1.git](https://github.com/phh02356-a11y/Meme-Engine-V1.git)
cd Meme-Engine-V1

# Install dependencies
pip install -e .
Configure your environment (.env)
PRIVATE_KEY=your_base58_private_key
RPC_URL=[https://your-rpc-endpoint.com](https://your-rpc-endpoint.com)
WS_URL=wss://your-ws-endpoint.com
Start the Bot
from pumpx import PumpXBot

bot = PumpXBot.from_config("config.yaml")
bot.run()
🛠 Configuration
All strategy parameters are managed in config.yaml:

YAML

rpc:
  priority_fee: 100000               # microlamports

monitor:
  platform: pump.fun
  min_liquidity_sol: 5               # filter threshold
  ignore_mint_authority: true        # safety check

strategy:
  buy_amount_sol: 0.1
  take_profit: 2.0                   # 2x exit
  stop_loss: 0.5                     # -50% cut
  slippage_bps: 500
📂 Project Structure
Plaintext

pump-x/
├── pumpx/
│   ├── bot.py           # Main loop and strategy orchestration
│   ├── monitor.py       # pump.fun WebSocket listener
│   ├── sniper.py        # Bonding curve detection logic
│   ├── swap.py          # Raydium & Jupiter execution
│   └── wallet.py        # Transaction signing & security
├── config.yaml          # Strategy configuration
└── .env.example         # Template for keys
⚖️ Disclaimer
This software is for educational and research purposes only. Cryptocurrency trading involves significant financial risk. The author is not responsible for any financial losses incurred. Never share your private key.

📄 License
This project is licensed under the MIT License.
