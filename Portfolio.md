# Julian Martinez — Full-Stack Web3 Portfolio

[github.com/Julian-dev28](https://github.com/Julian-dev28) · Senior Full-Stack Web3 Engineer

Selected work spanning Solidity / Solana / Stellar contracts, Node + Python backends,
and Next.js / React frontends — with on-chain integration end-to-end. Curated from
~30 active repos, newest first.

---

## Flagship

### [hermes-trader](https://github.com/Julian-dev28/hermes-trader) — *Autonomous multi-market trading agent on Hyperliquid*
Live trading agent that scans **230+ Hyperliquid perps** (crypto + equity + commodity)
in parallel, fires statistical triggers (price spikes, volume spikes, breakouts,
range compression, trend strength), and runs them through a multi-timeframe TA filter
(EMA, RSI, ATR, ADX, volume confirmation across 1h/4h/1d) *before* spending any AI
tokens. Only CONFIRMED setups reach the LLM — that pre-filter cut daily AI costs
from ~$8–$52 down to ~$3–$10 while improving signal quality. Confirmed signals
pass through **10 independent risk gates** (confidence, notional caps, daily loss,
cooldown, correlation, etc.) and are executed with **EIP-712 signed orders +
Kelly-sized SL/TP brackets** directly on Hyperliquid. Persistent file-backed agent
memory; **MCP server** exposes scan/research/execute/state tools to the Hermes Agent
runtime; clean separation between perception → triggers → TA → research → risk →
execution. No human in the loop.
**Stack:** TypeScript · Next.js 16 · Hyperliquid REST + WSS · OpenRouter (multi-model
LLM routing) · MCP · EIP-712 order signing · Hermes Agent (NousResearch) runtime
**Topics:** autonomous-trading, hyperliquid, perps, multi-market, llm, ta, mcp, eip712

### [flowpay](https://github.com/Julian-dev28/flowpay) — *EIP-712 signed crypto payments on Base*
Gasless payer-signed payment intents, settled by a relayer through a non-custodial
router. PaymentRouter does `SafeERC20.safeTransferFrom(payer → merchant)` after
verifying the EIP-712 signature, with per-(payer, nonce) replay protection and a
Pausable kill-switch. Backed by a Fastify orchestrator → BullMQ queue → tx-submitter
worker, a viem-based indexer with its own HTTP API, and a Next.js + wagmi +
RainbowKit frontend with a live allowance/sign/settle/index lifecycle stepper.
End-to-end runs locally on anvil with `pnpm stack`.
**Stack:** Solidity 0.8.26 · OpenZeppelin v5 · Foundry · Fastify 5 · BullMQ 5 ·
viem 2 · Next.js 15 · wagmi 2 · RainbowKit 2 · GitHub Actions CI
**Highlights:** 10/10 forge tests, 100% PaymentRouter coverage · permissionless
faucet endpoint · architecture + sequence Mermaid diagrams · production
observability hooks (Prometheus, structured pino logging, requestId tracing)

### [sentient-market-reader](https://github.com/Julian-dev28/sentient-market-reader) — *Live Kalshi algo trader, multi-agent AI*
TypeScript/Next.js prediction-market trading agent powered by a multi-agent
loop over Anthropic Claude or Grok, hooked into the Kalshi exchange.
**Stack:** TypeScript · Next.js · Anthropic · ROMA multi-agent framework
**Topics:** ai-agents, algotrading, prediction-markets, multi-agent, sentient-grid

---

## Trading & market making (full-stack)

### [aomi-trader](https://github.com/Julian-dev28/aomi-trader)
TypeScript automated trader.

### [polymarket-api-toolkit](https://github.com/Julian-dev28/polymarket-api-toolkit)
Polymarket CLOB clients + Polygon blockchain tracing + balance reconciliation
+ trading infrastructure. TypeScript end-to-end.

### [solana-arbitrage-scanner](https://github.com/Julian-dev28/solana-arbitrage-scanner)
High-performance Python Solana DEX arbitrage scanner.

### [Kalshi-Prediction-Market](https://github.com/Julian-dev28/Kalshi-Prediction-Market)
Anthropic-powered Kalshi market analyzer. TypeScript.

### [OKX-OS-Trading-Bot](https://github.com/Julian-dev28/OKX-OS-Trading-Bot) — *(2 stars)*
Telegram trading bot template on X Layer using OKX OS. End-to-end:
bot frontend, on-chain swap path, OKX OS DEX backend.

---

## DEX / swap integrations

### [okx-os-evm-swap-app](https://github.com/Julian-dev28/okx-os-evm-swap-app) — *(5 stars)*
EVM swap app demo wiring the OKX OS DEX API into a JavaScript frontend.

### [okx-dex-project](https://github.com/Julian-dev28/okx-dex-project) — *(4 stars)*
TypeScript reference implementation using the OKX DEX SDK.

### [dex-widget-demo](https://github.com/Julian-dev28/dex-widget-demo)
Boilerplate integrating the OKX OS DEX widget into a TypeScript app.

### [okx-dex-sdk](https://github.com/Julian-dev28/okx-dex-sdk) — *(2 stars)*
OKX DEX SDK in TypeScript.

### [okx_dex_tutorial](https://github.com/Julian-dev28/okx_dex_tutorial)
Tutorial: build an EVM DEX application end-to-end. MDX docs + code.

### [plugin-okx](https://github.com/Julian-dev28/plugin-okx) — *(3 stars)*
ElizaOS agent plugin that exposes the OKX DEX API to LLM agents.

### [WEB3-DEX-OPENSOURCE](https://github.com/Julian-dev28/WEB3-DEX-OPENSOURCE)
Solidity DEX contracts.

---

## Wallets, accounts, account abstraction

### [eip7702-demo](https://github.com/Julian-dev28/eip7702-demo)
**EIP-7702**: how to upgrade an EOA into a smart wallet. TypeScript demo of
the post-Pectra account-abstraction primitive.

### [fractal-wallet](https://github.com/Julian-dev28/fractal-wallet)
Wallet UI to track the Fractal ecosystem.

### [721-Credential](https://github.com/Julian-dev28/721-Credential)
EIP-712 + ERC-721/1155 credential contracts using OpenZeppelin AccessControl
+ ECDSA — a precursor to the EIP-712 patterns in FlowPay.
**Topics:** eip712, erc721, erc1155, evm, iam, security, solidity

---

## Multi-chain contract work

### [anchor-vault](https://github.com/Julian-dev28/anchor-vault)
Yield-bearing SPL token vault on Solana (Anchor) — configurable APR, per-position
accrual, authority-funded reward reserves.
**Stack:** Rust · Anchor · Solana

### [soroban-quickstart-dapp](https://github.com/Julian-dev28/soroban-quickstart-dapp) — *(2 stars)*
Stellar Soroban dApp with TypeScript frontend.

### [soroban-multisig-dapp](https://github.com/Julian-dev28/soroban-multisig-dapp)
Multisig dApp on Soroban.

### [sorovault](https://github.com/Julian-dev28/sorovault)
Vault contract on Soroban (Rust).

### [soroban-safe-counter](https://github.com/Julian-dev28/soroban-safe-counter)
Authorization-gated counter on Soroban.

### [consensus-hackathon-c2defi](https://github.com/Julian-dev28/consensus-hackathon-c2defi) — *(7 stars)*
Rust DeFi hackathon project — repo's top-starred entry.

### [solana-agent-project](https://github.com/Julian-dev28/solana-agent-project)
SendAI Solana agent with OKX DEX integration.

---

## AI + agent infrastructure

### [enterprise-ai-integration](https://github.com/Julian-dev28/enterprise-ai-integration)
Enterprise AI integration toolkit: HuggingFace, Grok, OpenRouter, RAG, FastAPI,
multi-model routing, cost tracking. Python backend, FastAPI surface.

### [roma-examples](https://github.com/Julian-dev28/roma-examples)
Runnable examples for the ROMA Recursive Open Meta-Agent framework — Python +
multi-agent + dspy + OpenRouter.

### [HyperMetric](https://github.com/Julian-dev28/HyperMetric)
Decentralized model comparison platform. Python.

### [decentralized-computing-demos](https://github.com/Julian-dev28/decentralized-computing-demos)
Decentralized compute examples.

### [allora-app](https://github.com/Julian-dev28/allora-app)
TypeScript app surfacing Allora network inferences via the SDK.

---

## Payments / merchant tooling

### [Beans-merchant-sdk-react-boilerplate](https://github.com/Julian-dev28/Beans-merchant-sdk-react-boilerplate)
Boilerplate for the Beans merchant SDK in React.

### [ncc-beerhole-contracts](https://github.com/Julian-dev28/ncc-beerhole-contracts)
Proof-of-concept Solidity contracts for crypto payments from buyer to bar.

### [m0-takehome](https://github.com/Julian-dev28/m0-takehome)
Solidity take-home (M^0 stablecoin protocol).

---

## Tooling, devrel, and templates

### [okx-os-solana-accelerate-hackathon](https://github.com/Julian-dev28/okx-solana-accelerate-hackathon)
OKX Solana Accelerate hackathon — DeFi templates for OKX DEX API on Solana.

### [devcon-builders-challenge](https://github.com/Julian-dev28/devcon-builders-challenge) — *(2 stars)*
Devcon builders challenge submission.

### [nextjs-boilerplate](https://github.com/Julian-dev28/nextjs-boilerplate)
Personal Next.js starter.

### [demos](https://github.com/Julian-dev28/demos) — *(1 star)*
Live demo workspace for SDK + protocol walkthroughs.

### [okx-dex-api-scripts](https://github.com/Julian-dev28/okx-dex-api-scripts)
Operator scripts hitting the OKX DEX API endpoints. TypeScript.

### [okx-rta-demo](https://github.com/Julian-dev28/okx-rta-demo)
RTA API demo on X Layer testnet.

### [bam-devrel-assignment](https://github.com/Julian-dev28/bam-devrel-assignment)
DevRel take-home.

### [ordinals-react-app-ts](https://github.com/Julian-dev28/ordinals-react-app-ts)
Ordinals (Bitcoin) React app, TypeScript.

### [multichain-memecoin-dashboard](https://github.com/Julian-dev28/multichain-memecoin-dashboard)
Multi-chain memecoin tracker dashboard.

---

## Stack at a glance

| Area | Tech I ship in production |
|---|---|
| **Smart contracts** | Solidity 0.8.x · OpenZeppelin v5 · Foundry · Hardhat · Soroban (Stellar) · Anchor (Solana) |
| **Backend** | Node.js · TypeScript · Fastify · BullMQ · Redis · pino · prom-client · Python · FastAPI |
| **Frontend** | Next.js 15 (App Router) · React 19 · TypeScript · wagmi 2 · viem 2 · RainbowKit 2 · TanStack Query 5 |
| **Tooling** | pnpm workspaces · Turborepo · GitHub Actions · Docker Compose · Zod |
| **Integrations** | OKX OS DEX · Hyperliquid · Polymarket CLOB · Kalshi · Allora · 0x · Trigger.dev · Supabase |
| **AI** | Anthropic Claude · Grok · OpenRouter · ROMA multi-agent · ElizaOS plugins · RAG |
