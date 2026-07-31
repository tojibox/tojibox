<div align="center">
  <img src="https://raw.githubusercontent.com/tojibox/tojibox-app/main/public/tojibox-wordmark.svg" alt="Tojibox" width="280" />
  <h3>The Due Diligence Platform for Real Estate</h3>
  <p>Verifiable zoning and parcel history, anchored on-chain. Built on <a href="https://docs.giwa.io">GIWA</a>, an OP-Stack EVM L2.</p>
</div>

---

## Vision

Tojibox's goal is to become the primary due-diligence platform for real estate in the United States: the place a real estate investor, attorney, lender, or Web3 protocol goes to get a fast, cryptographically verifiable zoning and parcel report. The model is live today in Wake County, NC (435,000+ parcels, on-chain oracle). Wake County is the pilot for a scraping and oracle architecture built to scale across all 3,000+ US counties, each holding the same siloed zoning data Wake County had.

## What Tojibox does

Real estate due diligence today, for investors, attorneys, lenders, and Web3 platforms tokenizing or lending against land alike, means paying third-party vendors thousands of dollars per deal, because county zoning history and rezoning-petition records are siloed, unstructured, and scattered across government portals.

Tojibox turns county parcel and rezoning data into a cryptographically verifiable on-chain oracle. Change events are Merkle-batched and committed to GIWA, due-diligence reports are ECDSA-signed by the oracle, and every issued report is minted as an on-chain ERC-721 receipt, so any counterparty can verify a report's authenticity in seconds by checking chain state directly instead of trusting Tojibox.

📄 **[Full architecture one-pager](../ONE-PAGER.md)**

## Repositories

| Repo | What it owns |
|---|---|
| [`tojibox-scraper`](https://github.com/tojibox/tojibox-scraper) | Parcel and rezoning-petition scraping (Wake County ArcGIS and Raleigh Planning), change detection, and the Merkle-commit pipeline that writes to `TojiboxOracle.sol` |
| [`tojibox-api`](https://github.com/tojibox/tojibox-api) | FastAPI oracle serving layer: parcel and petition endpoints, x402 payment gate, report signing, and the ERC-721 receipt mint via `TojiboxReportReceipt.sol` |
| [`tojibox-app`](https://github.com/tojibox/tojibox-app) | React/Vite frontend for the interactive parcel map, wallet-gated report downloads, and public report verification |

## On-chain (GIWA Sepolia testnet)

| Contract | Address |
|---|---|
| `TojiboxOracle` | [`0xDE4694B4A79E622E7Bc755707066932F7cdDFe30`](https://sepolia-explorer.giwa.io/address/0xDE4694B4A79E622E7Bc755707066932F7cdDFe30) |
| `TojiboxReportReceipt` (ERC-721) | [`0x5cF29e961631F78742c475f0aE77Ab779B2bEAf6`](https://sepolia-explorer.giwa.io/address/0x5cF29e961631F78742c475f0aE77Ab779B2bEAf6) |

## Tech stack

Python/FastAPI, PostgreSQL (Supabase), Solidity (Hardhat), Node.js/ethers.js, React/Vite, GIWA Sepolia (OP-Stack EVM L2, chain ID `91342`)
