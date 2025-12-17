Wallet-Gated AI - Trading Signals for Exclusive Access
AI agents that only work if authorized by Smart Contracts. A new paradigm for security and exclusivity in Web3.

License: MIT Node Python Ethereum

Executive Summary
Wallet-Gated AI is a platform demonstrating a revolutionary concept: artificial intelligence controlled by blockchain. A user connects their MetaMask wallet, a smart contract validates permissions, and a Python agent generates exclusive trading signals only for authorized users.

Key Features
Wallet Authentication: Secure MetaMask connection
On-Chain Verification: Smart Contract validates permissions in real-time
Intelligent Signals: Python agent analyzes market data
Exclusivity: Access restricted to authorized users
Transparency: Everything is auditable and verifiable on blockchain
Quick Start
Prerequisites
Node.js 18+
Python 3.12+
MetaMask installed in browser
Git
Installation (5 minutes)
# 1. Clone repository
git clone https://github.com/seu-repo/wallet-gated-ai.git
cd wallet-gated-ai

# 2. Install Frontend dependencies
npm install

# 3. Install Backend dependencies
cd agent
pip install -r requirements.txt
cd ..

# 4. Configure environment variables
cp .env.example .env
# Edit .env with your private keys and URLs

# 5. Start development server
npm run dev

# 6. In another terminal, start Python agent
cd agent
python agent_mvp.py
Ready! Access http://localhost:5173

Architecture
┌─────────────────────────────────────────────────────────┐
│                  Frontend (React + Vite)                │
│  ┌──────────────────────────────────────────────────┐  │
│  │ MetaMask Connection → Dashboard → Trading Signals│  │
│  └──────────────────────────────────────────────────┘  │
└────────────┬──────────────────────────────┬─────────────┘
             │                              │
    ┌────────▼────────┐            ┌────────▼────────┐
    │  Smart Contract │            │  Backend Python │
    │  (Sepolia)      │◄──────────►│  (Flask/Agent)  │
    │  SimpleOracle   │            │                 │
    └────────┬────────┘            └────────┬────────┘
             │                              │
             │                    ┌─────────▼─────────┐
             │                    │  CoinGecko API    │
             │                    │  (Market Data)    │
             │                    └───────────────────┘
             │
    ┌────────▼────────────────────┐
    │  Blockchain Sepolia Testnet │
    └─────────────────────────────┘
Components
Component	Technology	Purpose
Frontend	React 18 + TypeScript + Vite	User interface
Smart Contract	Solidity + Hardhat	Permission validation
Backend/Agent	Python + Flask + Web3.py	Signal analysis and generation
Data	CoinGecko API	Cryptocurrency prices
Network	Ethereum Sepolia	Development testnet
Project Structure
wallet-gated-ai/
├── src/                         # React Frontend
│   ├── components/              # Reusable components
│   │   ├── web3/               # Web3 components
│   │   ├── trading/            # Trading components
│   │   ├── dashboard/          # Dashboard
│   │   └── ui/                 # UI components
│   ├── hooks/                   # Custom hooks
│   ├── store/                   # Zustand stores
│   ├── lib/                     # Utilities
│   ├── pages/                   # Pages
│   ├── App.tsx                  # Root component
│   └── main.tsx                 # Entry point
│
├── agent/                       # Python Backend
│   ├── agent_mvp.py            # Main agent
│   ├── requirements.txt         # Python dependencies
│   └── .env.example            # Environment variables
│
├── contracts/                   # Smart Contracts
│   ├── SimpleOracle.sol        # Main contract
│   ├── scripts/                 # Deploy scripts
│   └── test/                    # Tests
│
├── public/                      # Static files
├── package.json                 # Node dependencies
├── vite.config.ts               # Vite configuration
├── tsconfig.json                # TypeScript configuration
├── tailwind.config.ts           # Tailwind CSS configuration
└── README.md                    # Documentation
Development
Available Commands
# Frontend
npm run dev          # Start development server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint

# Smart Contracts
npm run compile      # Compile contracts
npm run deploy       # Deploy to Sepolia
npm run test         # Run tests

# Backend
cd agent
python agent_mvp.py  # Run agent
Environment Variables
# Frontend
VITE_BACKEND_URL=http://localhost:5000

# Backend/Agent
SEPOLIA_RPC_URL=https://rpc.sepolia.org
PRIVATE_KEY=0x...
CONTRACT_ADDRESS=0x...
COINGECKO_API=https://api.coingecko.com/api/v3
User Flow
1. Wallet Connection
User clicks "Connect Wallet"
    ↓
MetaMask opens popup
    ↓
User authorizes access
    ↓
Frontend saves address in Zustand store
2. Permission Verification
Frontend queries Smart Contract
    ↓
Contract checks if wallet is authorized
    ↓
Returns true/false
    ↓
If true → Display Dashboard
If false → Display Access Gate
3. Signal Generation
Python agent connects to contract
    ↓
Reads secret strategy (authenticated)
    ↓
Fetches ETH price from CoinGecko
    ↓
Analyzes: ETH > $2000 USD?
    ↓
Generates signal: "BUY" or "WAIT"
    ↓
Records signal on blockchain
    ↓
Frontend displays to user
Security
Implemented Practices
Wallet Gating: Only authorized wallets access signals
Transaction Signing: Agent signs with private key
On-Chain Verification: Every action verified by smart contract
Environment Variables: Private keys never in code
Testnet: Safe development on Sepolia (not mainnet)
Future Security Checklist
[ ] External security audit
[ ] Multi-sig for critical operations
[ ] Rate limiting on APIs
[ ] Data encryption
[ ] Emergency circuit breaker
Testing
Frontend
npm run test         # Run tests with Vitest
npm run test:ui      # Vitest UI
Backend
cd agent
pytest               # Run Python tests
Smart Contracts
npm run test         # Run Hardhat tests
Monitoring
Check Signal on Blockchain
# View latest signal on Sepolia
curl -s https://rpc.sepolia.org \
  -X POST \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","method":"eth_call","params":[...],"id":1}'
Sepolia Dashboard
https://sepolia.etherscan.io/

Deployment
Frontend (Vercel)
# 1. Push to GitHub
git push origin main

# 2. Connect your repo on Vercel
# 3. Vercel deploys automatically

# Environment variables on Vercel:
# VITE_BACKEND_URL=https://your-backend.render.com
Backend (Render)
# 1. Create project on Render
# 2. Point to 'agent/' branch
# 3. Configure environment variables
# 4. Render deploys automatically
Smart Contract (Hardhat)
npm run deploy

# Save contract address in .env
CONTRACT_ADDRESS=0x...
Additional Documentation
README Complete - Full MVP documentation
WALLET_CONFIG - Wallet and network setup
PROJECT_SUMMARY - Technical overview
QUICKSTART - Quick start guide
ORACLE_MVP - Oracle details
Contributing
Fork the project
Create a branch for your feature (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request
Code Standards
Frontend: TypeScript + React Hooks + Tailwind CSS
Backend: Python 3.12+ with type hints
Contracts: Solidity ^0.8.0
Commits: Semantic messages (feat:, fix:, docs:, etc)
Troubleshooting
"Could not connect to MetaMask"
Check if MetaMask is installed
Try refreshing the page
Check if you're on Sepolia network
"Signal not appearing on dashboard"
Check if your wallet is authorized on contract
Wait for transaction confirmation
Check Python agent logs
"Error reading strategy from contract"
Check if PRIVATE_KEY is correct in .env
Check if CONTRACT_ADDRESS is valid
Try direct contract call on Etherscan
Roadmap
Phase 1: MVP (Completed)
[x] Smart Contract basic (SimpleOracle)
[x] Functional Python agent
[x] React frontend with MetaMask connection
[x] Deploy to Sepolia testnet
Phase 2: Enhancement (In Progress)
[ ] More interactive dashboard
[ ] Signal history tracking
[ ] Multi-asset support (not just ETH)
[ ] Strategy backtesting engine
Phase 3: Production (Future)
[ ] Security audit
[ ] Deploy on Ethereum mainnet
[ ] Signature system
[ ] Automatic trade execution
Support
Email: support@walletgatedai.com
Discord: Community
Issues: GitHub Issues
Twitter: @WalletGatedAI
License
This project is licensed under MIT. See LICENSE for details.

Acknowledgments
OpenAI for GPT
Ethereum community
Web3.py and Ethers.js teams
React and Vite communities
Built with heart for Web3

Last updated: December 17, 2025
