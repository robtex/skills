---
name: robtex-crypto
description: "Bitcoin and Lightning Network analysis — address balances, transaction tracing, block inspection, Lightning node/channel data, peer recommendations"
version: 1.0.3
author: Robtex
homepage: https://robtex.com
---

# Crypto Analysis

Analyze the Bitcoin or Lightning Network target: **$ARGUMENTS**

Auto-detect the input type and run appropriate tools:

## For a Bitcoin address (1..., 3..., bc1...):
1. `lookup_bitcoin_address` — balance, total received/sent, address type, abuse flags
2. `bitcoin_address_transactions` — recent transactions (paginated)
3. If abuse flags are present, highlight them prominently

## For a Bitcoin transaction (64-char hex):
1. `lookup_bitcoin_transaction` — inputs, outputs, fee, SegWit, size, mempool status
2. `bitcoin_transaction_spends` — which transactions consumed this tx's outputs

## For a Bitcoin block height (number):
1. `lookup_bitcoin_block` — header, transaction count, difficulty, timestamps

## For a Lightning node public key (66-char hex):
1. `lookup_lightning_node` — alias, capacity, channel count, addresses
2. `lookup_lightning_channels_per_node` — all channels for this node
3. `get_recommended_lightning_peers` — recommended peers to connect to

## For a Lightning node alias (text search):
1. `search_lightning_nodes_by_alias` — find matching nodes
2. Then look up the top result with `lookup_lightning_node`

## For a Lightning channel ID:
1. `lookup_lightning_channel` — capacity, nodes, status

## General queries:
- `bitcoin_blockchain_stats` — blockchain statistics over a block range
- `latest_lightning_channels` — most recently opened channels

Run tools in parallel where possible. Format amounts in BTC with sats equivalent. For transactions, show a clear flow diagram of inputs → outputs.
