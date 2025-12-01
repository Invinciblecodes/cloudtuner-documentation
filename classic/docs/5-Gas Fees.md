# Gas Fees & Web3 Recommendations - User Guide

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Gas Fees Calculator](#gas-fees-calculator)
4. [Understanding Gas Fees](#understanding-gas-fees)
5. [Gas Fee Trends](#gas-fee-trends)
6. [Web3 Business Recommendations](#web3-business-recommendations)
7. [Use Cases & Examples](#use-cases--examples)
8. [Tips & Best Practices](#tips--best-practices)
9. [FAQ](#faq)

---

## Introduction

### What is This Tool?

The Gas Fees & Web3 Recommendations tool helps you:

- **Track real-time gas fees** across multiple blockchain networks
- **Calculate transaction costs** in your preferred currency
- **Analyze 3-day trends** to find the best time to transact
- **Get business recommendations** for blockchain deployment decisions
- **Compare networks** based on cost, security, and performance

![Gas Fee Intelligence](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/gasfees_intelligence_page)

### Who Should Use This?

- **Crypto Users**: Save money on transactions by choosing optimal networks and timing
- **DApp Developers**: Make informed decisions about which blockchain to deploy on
- **Business Analysts**: Evaluate blockchain networks for enterprise use cases
- **NFT Creators**: Find cost-effective networks for minting and trading
- **DeFi Users**: Optimize costs for swaps, lending, and staking operations

---

## Getting Started

### Accessing the Tool

1. Navigate to the **Blockchain Gas Fee Intelligence** section
2. You'll see two main tabs:

   - **Gas Fees**: Real-time calculator and trends
   - **Recommendations**: Business-oriented network analysis

   ![Gas Fee Tabs](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/tabs+_gas_fee.png)

### Quick Start (3 Steps)

1. **Select your currency** (e.g., USD, EUR, JPY)
2. **Choose transaction type** (e.g., Simple Transfer, ERC-20 Transfer)
3. **Pick your speed** (Standard, Fast, or Instant)

![Select currency](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/selectcurrency.png)

The tool automatically shows you costs across all major networks!

---

## Gas Fees Calculator

### Step 1: Select Your Local Currency

**What it does:** Converts gas fees from cryptocurrency to your preferred currency.

**How to use:**

1. Click the **Currency** dropdown in the "Local Currency" card
2. Choose from 35+ currencies (USD, EUR, JPY, GBP, etc.)
3. All costs will update automatically

**Example:**

- Select "USD" → Costs shown in dollars ($)
- Select "EUR" → Costs shown in euros (€)
- Select "JPY" → Costs shown in yen (¥)

![Currency Dropdown](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/currencydropdown.png)

### Step 2: Choose Transaction Type & Gas Amount

**What it does:** Determines how much gas your transaction will use.

**How to use:**

1. Click the **Transaction Type** dropdown in the "Used Gas" card
2. Select your transaction type from 25+ options
3. Gas amount auto-fills (or enter custom amount)

![Used Gas](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/usedgaspopup.png)

**Common Transaction Types:**

| Transaction Type    | Gas Amount | Typical Use                       |
| ------------------- | ---------- | --------------------------------- |
| Simple Transfer     | 21,000     | Sending ETH/native tokens         |
| ERC-20 Transfer     | 65,000     | Sending tokens (USDT, USDC, etc.) |
| ERC-20 Approve      | 45,000     | Approving token spending          |
| Uniswap V2 Swap     | 150,000    | Token swaps on Uniswap V2         |
| Uniswap V3 Swap     | 180,000    | Token swaps on Uniswap V3         |
| NFT Mint            | 120,000    | Minting NFTs                      |
| NFT Transfer        | 85,000     | Transferring NFTs                 |
| OpenSea Sale        | 120,000    | Selling NFTs on OpenSea           |
| Compound Supply     | 200,000    | Supplying assets to Compound      |
| Aave Borrow         | 220,000    | Borrowing from Aave               |
| DeFi Staking        | 150,000    | Staking tokens                    |
| Contract Deployment | 500,000    | Deploying smart contracts         |

**Pro Tip:** If your transaction isn't listed, select "Custom" and enter the gas amount manually.

### Step 3: Select Transaction Speed

**What it does:** Determines how fast your transaction will be processed.

**Speed Options:**

| Speed        | Processing Time | Cost    | Best For                |
| ------------ | --------------- | ------- | ----------------------- |
| **Standard** | ~3-5 minutes    | Lowest  | Non-urgent transactions |
| **Fast**     | ~1-2 minutes    | Medium  | Regular transactions    |
| **Instant**  | ~15-30 seconds  | Highest | Urgent transactions     |

**How to use:**

1. Click one of the three speed buttons in the "Gas Price" card
2. Table updates with costs for your selected speed

**When to use each speed:**

- **Standard**: Sending funds to yourself, non-time-sensitive operations
- **Fast**: Regular DeFi operations, NFT purchases
- **Instant**: Time-sensitive trades, competitive NFT drops, arbitrage

---

## Understanding Gas Fees

### What Are Gas Fees?

Gas fees are transaction costs you pay to use a blockchain network. Think of them like:

- **Postage stamps** for sending mail
- **Toll fees** for using a highway
- **Processing fees** for credit card transactions

### Why Do Gas Fees Vary?

Gas fees change based on:

1. **Network Congestion**: More users = higher fees
2. **Transaction Complexity**: Complex operations cost more
3. **Transaction Speed**: Faster processing = higher fees
4. **Network Type**: Different blockchains have different fee structures

### Reading the Gas Fees Table

The table shows costs across multiple blockchain networks:

**Columns Explained:**

| Column               | What It Shows               | How to Use It                        |
| -------------------- | --------------------------- | ------------------------------------ |
| **Blockchain**       | Network name and logo       | Identify which blockchain            |
| **Type**             | Network category (L1/L2)    | Understand network architecture      |
| **Token**            | Native token and price      | See what you're paying with          |
| **Gas Price**        | Current gas price           | Compare prices across networks       |
| **Gas Used**         | Amount of gas needed        | Verify your transaction requirements |
| **Gas Current Cost** | Total cost in your currency | **This is what you'll pay!**         |

![Blockchain Table](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/blockchain_table.png)

**Example Reading:**

```
Blockchain: Ethereum
Type: Layer 1
Token: ETH ($3,500)
Gas Price: Standard (25.5 Gwei)
Gas Used: 21,000
Gas Current Cost: 1.87 USD
```

**Translation:** Sending ETH on Ethereum will cost you $1.87 at standard speed.

### Comparing Networks

**Look for:**

- ✅ **Lowest cost** for your transaction type
- ✅ **Acceptable speed** for your needs
- ✅ **Network security** (check Recommendations tab)
- ✅ **Token availability** (ensure your tokens exist on that network)

**Example Comparison:**

| Network  | Cost   | Speed  | Best For                                  |
| -------- | ------ | ------ | ----------------------------------------- |
| Ethereum | $1.87  | Medium | High-value transactions, maximum security |
| Polygon  | $0.001 | Fast   | Frequent transactions, gaming, NFTs       |
| Arbitrum | $0.15  | Fast   | DeFi operations, lower fees than Ethereum |
| Optimism | $0.12  | Fast   | DeFi, NFTs, general use                   |

---

## Gas Fee Trends

### 3-Day Gas Fee Trend & Recommendation

**What it shows:** The lowest-cost network over the past 3 days.

**How to read it:**

```
Lowest Cost Network: Polygon
Average cost over last 3 days: $0.000123

Standard: $0.000100
Fast: $0.000123
Instant: $0.000150
```

**What this means:**

- Polygon has been the cheapest network for the past 3 days
- Standard transactions averaged $0.0001
- You can expect similar costs if you transact now

**How to use this:**

- ✅ Choose this network for cost savings
- ✅ Verify your tokens/dApp are available on this network
- ✅ Consider security needs (check Recommendations tab)

### Individual Network Charts

**What they show:** 3-day price trends for each blockchain network.

**How to read the charts:**

1. **Chart Title**: Network name (e.g., "Ethereum Gas Fee")
2. **Trend Indicator**:
   - 🔺 **Red arrow up** = Prices increasing
   - 🔻 **Green arrow down** = Prices decreasing
   - **Percentage** = How much prices changed
3. **Current Price**: Latest price for selected speed
4. **Graph**: Visual trend over 3 days
5. **Speed Buttons**: Switch between Standard/Fast/Instant

![Gas Trends](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/gastrends.png)

**Example Chart Reading:**

```
Ethereum Gas Fee
Last 3 Days | 🔺 +15.3%

Current Standard Price: $1.87

[Graph showing upward trend]

[Standard] [Fast] [Instant] ← Click to switch
```

**What this tells you:**

- Ethereum fees increased 15.3% over 3 days
- Current standard price is $1.87
- Trend is upward → Consider waiting or using cheaper network

### Using Trends to Save Money

**Strategy 1: Wait for Lower Fees**

- If trend shows 🔺 increasing prices → Wait if not urgent
- If trend shows 🔻 decreasing prices → Good time to transact

**Strategy 2: Choose Optimal Network**

- Compare trends across networks
- Pick network with stable or decreasing fees

**Strategy 3: Time Your Transactions**

- Look for dips in the 3-day chart
- Transact during low-activity periods

**Pro Tips:**

- 📊 Check trends before large transactions
- ⏰ Weekend fees are often lower than weekdays
- 🌙 Late night (UTC) often has lower fees
- 🔄 Refresh data regularly for latest prices

---

## Web3 Business Recommendations

### Overview

The **Recommendations** tab provides business-oriented analysis to help you choose the right blockchain for your project.

**Who should use this:**

- 🏢 Businesses evaluating blockchain deployment
- 👨‍💻 Developers choosing a network for their dApp
- 📊 Analysts comparing blockchain options
- 💼 Decision-makers planning Web3 strategy

### Overall Best Network Card

**What it shows:** The top-ranked blockchain based on comprehensive analysis.

**Key Information:**

1. **Network Name & Score**

   - Overall score out of 5.0
   - Higher score = better overall performance

2. **Strengths** (Green Card)

   - What this network does well
   - Competitive advantages
   - Example: "Lowest transaction costs", "Fast confirmation times"

3. **Weaknesses** (Red Card)

   - Areas where network falls short
   - Potential concerns
   - Example: "Lower security score than Ethereum", "Smaller ecosystem"

4. **Best For** (Orange Card)

   - Ideal use cases for this network
   - Recommended applications
   - Example: "High-frequency transactions", "Gaming applications", "NFT marketplaces"

5. **Deployment Costs**
   - **Smart Contract**: Cost to deploy a contract
   - **Transaction**: Average transaction cost
   - **Storage**: Cost to store data on-chain
   - **Security**: Security-related costs (audits, etc.)

**Example Reading:**

```
⭐ Polygon
Overall Best Network
Score: 4.5/5.0

Strengths:
✅ Lowest transaction costs
✅ Fast confirmation times
✅ Large ecosystem

Weaknesses:
⚠️ Lower security score than Ethereum
⚠️ Centralization concerns

Best For:
🔥 High-frequency transactions
🔥 Gaming applications
🔥 NFT marketplaces

Deployment Costs:
Smart Contract: $0.50
Transaction: $0.0001
Storage: $0.0005
Security: $0.0002
```

![Overall Expenses](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/overallexpenses.png)

**How to use this:**

- ✅ Start with the best network recommendation
- ✅ Review strengths to confirm it meets your needs
- ✅ Check weaknesses to identify potential issues
- ✅ Verify your use case matches "Best For" list
- ✅ Compare deployment costs to your budget

---

### Use Case Specific Recommendations

**What it shows:** Top 3 networks for specific business scenarios.

![Usecase Specific](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/usecasespecific.png)

**Available Use Cases:**

1. **Smart Contract Deployment**

   - Best networks for deploying smart contracts
   - Focuses on deployment costs and reliability
   - Shows additional ranking by lowest deployment cost

2. **High-Frequency Transactions**

   - Best networks for frequent transactions
   - Focuses on speed and low per-transaction costs
   - Shows additional ranking by highest security

3. **NFT Marketplace**

   - Best networks for NFT platforms
   - Balances cost, speed, and ecosystem

4. **DeFi Protocol**
   - Best networks for DeFi applications
   - Focuses on security, liquidity, and composability

**How to use:**

1. **Select Your Use Case**

   - Click the button matching your project type
   - Example: Click "Smart Contract Deployment" if you're launching a dApp

2. **Review Top 3 Networks**

   - Each network shows:
     - **Rank**: 1st, 2nd, or 3rd place
     - **Network Name**: Which blockchain
     - **Reasoning**: Why it's recommended
     - **Estimated Cost**: Expected costs
     - **Score**: Numerical rating

3. **Compare Rankings**
   - Look at reasoning for each network
   - Compare estimated costs
   - Consider scores (higher = better)

**Example: Smart Contract Deployment**

```
Top Networks for Smart Contract Deployment:

1️⃣ Polygon
   Reasoning: Lowest deployment costs with good security
   Estimated Cost: $0.50
   Score: 4.5

2️⃣ Arbitrum
   Reasoning: Low costs with Ethereum security
   Estimated Cost: $2.50
   Score: 4.3

3️⃣ Optimism
   Reasoning: Cost-effective with strong ecosystem
   Estimated Cost: $3.00
   Score: 4.2

Top 3 Networks by Cost Effectiveness:
1. Polygon - $0.50
2. Arbitrum - $2.50
3. Optimism - $3.00
```

**Decision Framework:**

| Priority           | Choose Network Based On                              |
| ------------------ | ---------------------------------------------------- |
| **Lowest Cost**    | Look at "Cost Effectiveness" ranking                 |
| **Best Security**  | Look at "Security" ranking (High-Frequency use case) |
| **Balanced**       | Use the main Top 3 ranking                           |
| **Specific Needs** | Read the "Reasoning" for each network                |

---

## Use Cases & Examples

### Example 1: Sending Crypto to a Friend

**Scenario:** You want to send $100 worth of USDC to a friend.

**Steps:**

1. Go to **Gas Fees** tab
2. Select currency: **USD**
3. Select transaction type: **ERC-20 Transfer**
4. Select speed: **Standard** (not urgent)
5. Review table results:

| Network  | Cost   | Time   |
| -------- | ------ | ------ |
| Ethereum | $1.87  | ~3 min |
| Polygon  | $0.001 | ~2 min |
| Arbitrum | $0.15  | ~2 min |

**Decision:** Use **Polygon** to save $1.87 in fees!

**Savings:** 99.9% cheaper than Ethereum

---

### Example 2: Minting an NFT Collection

**Scenario:** You're launching a 10,000 NFT collection.

**Steps:**

1. Go to **Recommendations** tab
2. Select use case: **NFT Marketplace**
3. Review top networks:

   - Polygon: Low cost, fast, large NFT ecosystem
   - Ethereum: Highest security, most valuable NFTs
   - Arbitrum: Balance of cost and security

4. Check deployment costs in "Overall Best Network" card
5. Calculate total costs:
   - Polygon: $0.50 (contract) + $0.0001 × 10,000 (mints) = **$1.50**
   - Ethereum: $50 (contract) + $0.01 × 10,000 (mints) = **$150**

**Decision:** Use **Polygon** for cost-effective launch, or **Ethereum** for premium positioning.

**Savings:** $148.50 by using Polygon

---

### Example 3: Running a DeFi Protocol

**Scenario:** You're building a lending protocol.

**Steps:**

1. Go to **Recommendations** tab
2. Select use case: **DeFi Protocol**
3. Review recommendations:

   - Check security scores (critical for DeFi)
   - Review ecosystem compatibility
   - Consider liquidity availability

4. Review "Overall Best Network" strengths/weaknesses
5. Check deployment costs for smart contracts

**Decision Factors:**

- ✅ Security score > 4.0
- ✅ Strong DeFi ecosystem
- ✅ Reasonable deployment costs
- ✅ Good liquidity

**Typical Choice:** Ethereum (security) or Arbitrum (cost + security)

---

### Example 4: High-Frequency Trading Bot

**Scenario:** You're running a trading bot that makes 1,000 transactions per day.

**Steps:**

1. Go to **Gas Fees** tab
2. Select transaction type: **Uniswap V3 Swap**
3. Select speed: **Fast**
4. Calculate daily costs:

| Network  | Per Transaction | Daily Cost (1,000 tx) |
| -------- | --------------- | --------------------- |
| Ethereum | $5.00           | $5,000                |
| Polygon  | $0.01           | $10                   |
| Arbitrum | $0.50           | $500                  |

5. Go to **Recommendations** tab
6. Select: **High-Frequency Transactions**
7. Check security rankings (important for large volumes)

**Decision:** Use **Polygon** for cost savings, ensure security measures are in place.

**Monthly Savings:** $149,700 vs Ethereum!

---

### Example 5: Deploying a Gaming dApp

**Scenario:** You're building a blockchain game with frequent in-game transactions.

**Steps:**

1. Go to **Recommendations** tab
2. Review "Overall Best Network" → Check "Best For" section
3. Look for "Gaming applications" in the list
4. Select use case: **High-Frequency Transactions**
5. Review top networks for gaming:
   - Low transaction costs (players transact often)
   - Fast confirmation (good UX)
   - Large ecosystem (more players)

**Key Metrics:**

- Transaction cost < $0.01 (players won't pay high fees)
- Confirmation time < 5 seconds (smooth gameplay)
- Deployment cost < $5 (reasonable for indie developers)

**Typical Choice:** Polygon or Immutable X (gaming-focused)

---

## Tips & Best Practices

### Cost Optimization Tips

**1. Choose the Right Network**

- ✅ Use Layer 2 networks (Polygon, Arbitrum, Optimism) for lower fees
- ✅ Reserve Ethereum for high-value or security-critical transactions
- ✅ Check if your tokens/dApp are available on cheaper networks

**2. Time Your Transactions**

- ⏰ Transact during off-peak hours (weekends, late night UTC)
- 📊 Check 3-day trends before large transactions
- 🔻 Wait for downward trends if not urgent

**3. Batch Transactions**

- 📦 Combine multiple operations into one transaction
- 💰 Pay gas fees once instead of multiple times
- 🔧 Use multi-send contracts for bulk transfers

**4. Use Appropriate Speed**

- 🐌 Standard for non-urgent transactions (save 30-50%)
- ⚡ Fast for regular operations (balanced)
- 🚀 Instant only when absolutely necessary (costs 50-100% more)

**5. Monitor Gas Prices**

- 📱 Check this tool regularly
- 🔔 Set up alerts for low gas prices (future feature)
- 📈 Learn your network's gas patterns

### Security Best Practices

**1. Verify Network Security**

- ✅ Check security scores in Recommendations tab
- ✅ Higher scores for high-value transactions
- ✅ Research network's security track record

**2. Understand Trade-offs**

- ⚖️ Lower cost often means lower security
- ⚖️ Newer networks may have undiscovered vulnerabilities
- ⚖️ Balance cost savings with risk tolerance

**3. Use Established Networks for Large Amounts**

- 💎 Ethereum for transactions > $10,000
- 🛡️ Proven security for valuable assets
- 📜 Longer track record = more confidence

**4. Test First**

- 🧪 Send small test transaction first
- ✅ Verify it works on the chosen network
- 💰 Then send larger amounts

### Decision-Making Framework

**For Individual Users:**

```
Is it urgent?
├─ Yes → Use Fast/Instant speed
└─ No → Use Standard speed

Is the amount > $1,000?
├─ Yes → Use Ethereum or high-security network
└─ No → Use cheapest network (Polygon, etc.)

Do you transact frequently?
├─ Yes → Prioritize low-cost networks
└─ No → Cost less important, focus on security
```

**For Businesses/Developers:**

```
What's your use case?
├─ DeFi → High security (Ethereum, Arbitrum)
├─ Gaming → Low cost + speed (Polygon)
├─ NFTs → Depends on target market
│   ├─ Premium → Ethereum
│   └─ Mass market → Polygon
└─ Enterprise → High security (Ethereum)

What's your budget?
├─ Limited → Layer 2 networks
├─ Moderate → Arbitrum, Optimism
└─ Unlimited → Ethereum (best security)

What's your transaction volume?
├─ High (>1000/day) → Must use low-cost network
├─ Medium (100-1000/day) → Balance cost/security
└─ Low (<100/day) → Security more important
```

### Common Mistakes to Avoid

**❌ Don't:**

- Use Instant speed for non-urgent transactions (wastes money)
- Ignore 3-day trends (miss cost-saving opportunities)
- Choose network based only on cost (security matters!)
- Forget to verify token availability on chosen network
- Transact during peak hours without checking fees

**✅ Do:**

- Compare multiple networks before transacting
- Check trends for large transactions
- Balance cost with security needs
- Test with small amounts first
- Use appropriate transaction speed

### Pro Tips from Experienced Users

**💡 Tip 1: The "Weekend Discount"**

- Gas fees typically drop 20-40% on weekends
- Plan non-urgent transactions for Saturday/Sunday
- Check trends to confirm the pattern

**💡 Tip 2: The "Layer 2 Strategy"**

- Keep funds on Layer 2 for daily use
- Only bridge to Ethereum when necessary
- Save 90%+ on transaction costs

**💡 Tip 3: The "Batch Everything" Approach**

- Accumulate multiple operations
- Execute all at once to save gas
- Especially effective for NFT minting

**💡 Tip 4: The "Network Diversification"**

- Don't put all assets on one network
- Spread across 2-3 networks
- Balance security and cost

**💡 Tip 5: The "Trend Watcher"**

- Check trends daily for a week
- Learn your network's patterns
- Transact during predictable low periods

---

---

_Last Updated: December 2025_  
_Version: 1.0.0_  
_© 2025 Cloudtuner.ai. All rights reserved._

<!-- Shriyansh agarwal | December 1, 2025, 12:29 -->
