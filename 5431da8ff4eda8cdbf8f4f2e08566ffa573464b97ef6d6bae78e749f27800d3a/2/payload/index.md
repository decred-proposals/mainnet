RFP: Decred Decentralized Exchange Infrastructure
RFP: Decred Decentralized Exchange Infrastructure

## Abstract

Existing cryptocurrency exchange platforms fall into 4 overlapping categories: custodial corporate entities, services, tokens, and blockchains.  This proposal describes a new type of cryptocurrency-only decentralized exchange based on open source software that will allow cross-chain trading to occur directly between users, with minimal fees and a simple client-server architecture.  Market and limit orders on the server will be matched pseudorandomly within epochs, to reduce incentives to frontrun order flow.  Clients will pay a fee to each server for each account they use as a means to discourage malicious behavior.  Clients will communicate with the server and cryptocurrency wallets, so they can communicate order data and create atomic swaps, monitor, and redeem scripts on the corresponding blockchains.  The server will be non-custodial and it will act as a relay for messages between clients trading a given cryptocurrency pair.

## Motivation

Existing cryptocurrency exchanges are all setup as businesses, either directly or indirectly, where the goal is for an operator to profit from fees, paid by clients, or the value of an underlying token or blockchain. The proposed decentralized exchange infrastructure addresses the following issues:

* Unnecessary 3rd parties: [Atomic swaps](https://github.com/decred/atomicswap) demonstrate that exchange intermediaries are unnecessary, so it is natural to remove them.  The server will only assist in the price discovery and order matching process, and it will be entirely non-custodial.
* Liquidity is permissioned: Instead of convincing exchanges to integrate a cryptocurrency and various trading pairs, developers can add support for their project and trading pairs directly via atomic swaps.
* Per-trade fees incentivize centralization: Servers will only use fees for client accounts to discourage malicious clients, and there will be no per-trade fees.
* Frontrunning by low-latency clients: Market and limit orders will be matched using a pseudorandom process in epochs, so that low-latency clients cannot frontrun higher-latency clients.  This will protect market liquidity from external gaming.
* Exchange opacity: All trade data handled by client and server will be cryptographically signed, so that both client and server have a verifiable record of activity.  Malicious behavior on part of clients and servers can be demonstrated publicly and independently verified.  Trading volume can be directly verified on-chain.
* Resilience to threats: A simple client-server architecture means that if any server is taken down, another server can take its place with minimal work on part of clients and server operators.

By addressing these issues with existing exchanges, it is possible to create a more transparent, fair and resilient exchange process between cryptocurrencies.  These points have addressed in greater detail in a [blog from June 2018](https://blog.decred.org/2018/06/05/A-New-Kind-of-DEX/).

This improved exchange infrastructure will benefit Decred directly, by making the exchange process more permissionless and less gameable, thereby increasing its accessibility and lowering the risks of market making.  However, it will also benefit the overall cryptocurrency ecosystem as a piece of common infrastructure, which we can use as a marketing tool.

## Implementation

What follows is a summary of how the various processes involved in the exchange work.  It is intended to be used by development contractors who implement the exchange as a basis for their bidding and work they perform.  Note that this pseudocode only addresses certain negative paths and focuses on the positive path for sake of clarity and brevity.  Contractors will be expected to handle all negative paths properly, despite their not being exhaustively enumerated here.

client-wallet: create market or limit order

* client chooses an amount they wish to use for a limit or market order and sends this to a wallet they control for chain A
* wallet A selects one or more UTXOs or similar that sum to greater than or equal to the amount specified
* client requests a new address from wallet B to include in the order
* client requests wallet A signs the order, ((amount, rate, chain A UTXOs, chain B address)), using the corresponding private keys to demonstrate control of funds

client-wallet: create cancel order

* client requests wallet signs the cancel order, which reference the corresponding limit order, e.g. ((limit order hash)), using the corresponding private keys to demonstrate control of funds

client-server: request account

* client connects to server and both identify themselves using a long-lived PKI keypair
* server responds with a fee the client must pay to get an account on the server
* client pays the fee and server gives the client’s long-lived PKI public key access to one or more markets

client-server: submit limit order

* client submits limit order as a signed message that includes the unspent funds for the order, an amount, and a rate (other side of a pair), where signatures demonstrate control of the unspent funds and the long-lived identity of the client
* server receives the order, adds the time, signs it, stores it and replies to the client with the signed order
* server broadcasts the limit order to other connected clients, after removing the identity signature, and adds it to its order book

client-server: submit cancel order

* client submits cancel order as a signed message that references the corresponding open limit order, where signatures demonstrate control of the unspent funds and the long-lived identity of the client
* server receives the order, adds the time, signs it, stores it and replies to the client with the signed order
* server broadcasts the cancel order to other connected clients, after removing the identity signature, and removes the corresponding limit order from its order book

client-server: submit market order

* client submits market order as a signed message that includes unspent funds for the order, an amount, and a time, where signatures demonstrate control of the unspent funds and the long-lived identity of the client
* server receives the order, adds the time, signs it, stores it and replies to the client with the signed order
* server accumulates a queue of limit orders and matches them (see below for details) with limit orders once an epoch
* server signs and publishes the matched orders, after removing the identity signatures, at the end of the epoch, updates order book (E1)
* client submitting market order initiates an atomic swap on chain A
* client submits their atomic swap contract to the server, adds the time, signs with identity key
* server verifies the atomic swap is properly initiated (E2)
* server relays the atomic swap contract to the client with the matched limit order, adds time, signs message (E3)
* client with limit order verifies the swap
* client with limit order performs step 2 of atomic swap on chain B
* server verifies the atomic swap step 2 occurs properly (E4)
* client with market order redeems on chain B
* server verifies the chain B redeem occurred (E5)
* client with limit order redeems on chain A
* server verifies the chain A redeem occurred (E6)

client-server: request current order book

* client requests server send the latest snapshot of the order book, adds time, signs message
* server sends most recent aggregated copy of the order book, adds time, signs message
 
server-internal: order matching

* client market orders accumulate in a queue on the server during each epoch
* at end of epoch, market orders in queue are concatenated and hashed, and that hash is used to determine the sequence in which orders are matched against order book, using FIFO on the order book side
* server takes matching summary for epoch, adds time, signs it and broadcasts to all connected clients

client-server: historical data requests

* client authenticates to server and requests historical data
* server replies with historical data to client, likely requires some limits

In addition to the various processes that must be supported, there are several core components that must be completed:

* Engineering specification: create a full RFC-style specification for the processes described in this proposal prior to code being written
* CLI client: interacts with wallets and server by preparing signed orders, submitting orders, tracking orders, completing orders via swaps, and storing order receipts
* CLI server: acts as a meeting point for clients, assists in atomic swap process, uses a paywall for client accounts, broadcasting client orders, matching client orders, and publishing matches each epoch
* GUI client: integrates with existing Decrediton wallet and other wallets

Ideally, this work would be performed in Go, using gRPC and JSON-RPC with TLS (where possible) to connect to consensus daemons and wallets, and gRPC with TLS to connect to the server.  A minimum viable product will support a DCR/BTC trading pair, with other pairs to be added at a later date.

## Contractors

This is an RFP (Request For Proposal), where we are assessing stakeholder sentiment before soliciting any bids to complete this work.  If this proposal passes, contractors will be chosen at a later date, per stakeholder preference.

## Timeline

It should be possible to complete this in less than 6 months.

## Projected Cost

It is estimated this work will cost between USD 100,000 and 250,000 to complete.

## Future Work

Assuming the minimum viable product works reasonably well, consider creating a server mesh with an aggregated order book and a politeia-based reputation system for clients and servers.

## Notable Changes

* Removed reputation system component since it is not necessary until a server mesh and order book aggregation occur.  This suggestion was made by matrix user isuldor.
* Substantially reduced the upper bound on projected cost from USD 1,000,000 to USD 250,000, per feedback in the comments.
* Added a link to the original DEX blog post for easier reference.