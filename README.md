# Token Unlock Calculator

A lightweight Web3 tool for exploring token unlocks, circulating supply growth, and hypothetical selling scenarios.

Enter an unlock amount, token price, and duration to see how supply changes and compare different selling assumptions.

## Live Demo

[Open Token Unlock Calculator](https://george2655.github.io/token-unlock-calculator/)

## Features

- Calculate circulating supply growth after an unlock
- Estimate unlock value at a fixed token price
- Calculate daily token unlocks
- Model a custom percentage of unlocked tokens being sold
- Compare 10%, 25%, 50%, and 100% selling scenarios
- Include and highlight your custom selling percentage
- Compare hypothetical daily selling with daily trading volume
- Display a circulating supply projection chart
- Estimate market capitalization after the unlock at a fixed price
- Switch between light and dark themes
- Remember your theme preference
- Validate inputs and handle zero circulation or trading volume
- Responsive layout for desktop and mobile

## How to Use

1. Enter the total token supply and current circulating supply.
2. Enter the upcoming unlock amount.
3. Set the token price and unlock duration.
4. Choose the percentage of unlocked tokens assumed to be sold.
5. Enter average daily trading volume in USD.
6. Click **Calculate scenario**.

Use **1 day** to model a single-day cliff unlock. Longer durations assume equal daily unlocks and evenly distributed selling.

The comparison table uses the same inputs for every scenario, changing only the percentage sold.

## Example

Using these inputs:

| Input | Value |
| --- | ---: |
| Total token supply | 1,000,000,000 |
| Current circulating supply | 150,000,000 |
| Upcoming unlock | 30,000,000 |
| Token price | $0.05 |
| Unlock duration | 30 days |
| Share sold | 25% |
| Average daily trading volume | $500,000 |

The calculator returns:

| Result | Value |
| --- | ---: |
| Circulating supply growth | 20% |
| New circulating supply | 180,000,000 |
| Unlock / total supply | 3% |
| Total unlock value | $1,500,000 |
| Tokens unlocked per day | 1,000,000 |
| Hypothetical total selling | $375,000 |
| Hypothetical daily selling | $12,500 |
| Daily selling / daily volume | 2.5% |
| Market cap after unlock at fixed price | $9,000,000 |

### Selling Scenario Comparison

| Share sold | Tokens sold | Total selling | Daily selling | Daily selling / volume |
| --- | ---: | ---: | ---: | ---: |
| 10% | 3,000,000 | $150,000 | $5,000 | 1% |
| 25% | 7,500,000 | $375,000 | $12,500 | 2.5% |
| 50% | 15,000,000 | $750,000 | $25,000 | 5% |
| 100% | 30,000,000 | $1,500,000 | $50,000 | 10% |

## Calculation Logic

| Metric | Formula |
| --- | --- |
| New circulating supply | Current circulating supply + unlock amount |
| Circulating supply growth (%) | Unlock amount ÷ current circulating supply × 100 |
| Unlock / total supply (%) | Unlock amount ÷ total supply × 100 |
| Unlock value | Unlock amount × token price |
| Daily unlocked tokens | Unlock amount ÷ duration |
| Tokens sold | Unlock amount × share sold ÷ 100 |
| Total selling value | Unlock value × share sold ÷ 100 |
| Daily selling value | Total selling value ÷ duration |
| Daily selling / volume (%) | Daily selling value ÷ daily trading volume × 100 |
| Market cap after unlock | New circulating supply × token price |

Supply growth is shown as **N/A** when current circulation is zero. The volume ratio is shown as **N/A** when daily trading volume is zero.

## Model Assumptions

- All unlocked tokens enter circulating supply.
- Token price and daily trading volume stay fixed.
- Unlocks and hypothetical selling are spread evenly across the entered duration.
- Selling percentages are user-defined assumptions.
- The chart shows a linear supply projection.
- Trading volume is not a measure of order-book liquidity.
- The selling-to-volume ratio does not predict a percentage price drop.
- Inputs are entered manually; no live market data is fetched.

This tool provides scenario estimates for educational use, not investment advice.

## Tech Stack

- HTML5
- CSS3
- Vanilla JavaScript
- SVG chart
- LocalStorage for theme preference
- GitHub Pages

No frameworks, external libraries, API keys, or build step required.

## Run Locally

Clone the repository:

```bash
git clone https://github.com/george2655/token-unlock-calculator.git
