

## 🧠 Full-Stack Blockchain Developer Interview Task  
**Goal:** Build a seamless multi-chain dApp that allows users to **Swap Tokens** in one smooth transaction.

---

## 🎯 What You’ll Build

A user-friendly dApp that:
- Lets users connect wallets on **Ethereum, Polygon, Arbitrum**
- Swap tokens (e.g., USDC → DAI or any ERC20)
- Includes a **1% platform fee** on swaps
- Features a **clean, responsive UI** with charts and status updates

---

## 🛠️ Project Structure

### 🔗 1. Multi-Chain Wallet UI
- Connect wallet via `RainbowKit` or `Web3Modal`
- Detect and display:
  - Chain name and token balances (ETH, MATIC, ARB + ERC20s)
  - Wallet address
- Allow chain switching
- Highlight selected token pair for swapping

---

### ⚙️ 2. Smart Contract: Token Swap with Fee

- Accept a token from the user
- Apply **1% fee** (transfer to feeRecipient)
- Swap remaining amount using **Uniswap V3 or 1inch Router**
- Emit `SwapExecuted(address user, address inputToken, address outputToken, uint256 amountIn, uint256 amountOut)`

#### Key Features:
- Uses `SafeERC20` from OpenZeppelin
- Protects with slippage (`minAmountOut`)
- Supports gasless approval via `permit()` (optional)
- Uses a single `swap()` function

---

### 🖥️ 3. Frontend Integration

- Select input/output tokens (e.g., USDC → DAI)
- Input amount
- Submit flow:
  - Approve token (if needed)
  - Call `swap()` contract function
- Display:
  - Swap status (loading → success/fail)
  - Transaction hash + block explorer link
  - Breakdown of:
    - Input amount
    - Fee deducted
    - Amount swapped

---

### 📊 4. Bonus Features (Optional)

- Live price chart via Uniswap Subgraph or Dexscreener
- Slippage setting slider
- Confetti/animation on success
- Swap history tracker (local or subgraph-based)
- Custom token list from CoinGecko API

---

## 📁 Deliverables

1. GitHub repo with:
   ```
   /contracts
   /frontend
   README.md
   ```
2. README should include:
   - Setup instructions
   - Contract address (testnet)
   - Screenshots or live demo (optional)
   - Notes on architecture decisions

---

## ✅ Evaluation Rubric

| Area                         | Weight |
|------------------------------|--------|
| Smart Contract Quality       | 35%    |
| Frontend UI/UX               | 25%    |
| Blockchain Integration       | 20%    |
| End-to-End Functionality     | 10%    |
| Code Quality & Structure     | 10%    |
| **Bonus Features**           | +X%    |

