<div align="center">
  <img src="https://raw.githubusercontent.com/tojibox/tojibox-app/main/public/tojibox-wordmark.svg" alt="Tojibox" width="280" />
  <h3>Decentralized Land Registry & Due Diligence Protocol</h3>
  <p>Built on <a href="https://docs.giwa.io">GIWA</a> — an OP-Stack EVM L2</p>
</div>

---

## What Tojibox does

Web3 platforms that tokenize land or lend against real estate — RWA protocols, fractional-ownership platforms, on-chain lenders — currently pay third-party vendors thousands of dollars per deal for zoning due diligence, because county zoning history and rezoning-petition records are siloed, unstructured, and scattered across government portals.

Tojibox turns Wake County, NC parcel and rezoning data into a cryptographically verifiable on-chain oracle: change events are Merkle-batched and committed to GIWA, due-diligence reports are ECDSA-signed by the oracle, and every issued report is minted as an on-chain ERC-721 receipt — so any counterparty can verify a report's authenticity in seconds by checking chain state directly, not by trusting Tojibox.

## Repositories

| Repo | What it owns |
|---|---|
| [`tojibox-scraper`](https://github.com/tojibox/tojibox-scraper) | Parcel/rezoning-petition scraping (Wake County ArcGIS + Raleigh Planning), change detection, and the Merkle-commit pipeline that writes to `TojiboxOracle.sol` |
| [`tojibox-api`](https://github.com/tojibox/tojibox-api) | FastAPI oracle serving layer — parcel/petition endpoints, x402 payment gate, report signing, and the ERC-721 receipt mint via `TojiboxReportReceipt.sol` |
| [`tojibox-app`](https://github.com/tojibox/tojibox-app) | React/Vite frontend — interactive parcel map, wallet-gated report downloads, and public report verification |

## On-chain (GIWA Sepolia testnet)

| Contract | Address |
|---|---|
| `TojiboxOracle` | [`0xDE4694B4A79E622E7Bc755707066932F7cdDFe30`](https://sepolia-explorer.giwa.io/address/0xDE4694B4A79E622E7Bc755707066932F7cdDFe30) |
| `TojiboxReportReceipt` (ERC-721) | [`0x5cF29e961631F78742c475f0aE77Ab779B2bEAf6`](https://sepolia-explorer.giwa.io/address/0x5cF29e961631F78742c475f0aE77Ab779B2bEAf6) |

## Tech stack

Python/FastAPI · PostgreSQL (Supabase) · Solidity (Hardhat) · Node.js/ethers.js · React/Vite · GIWA Sepolia (OP-Stack EVM L2, chain ID `91342`)
