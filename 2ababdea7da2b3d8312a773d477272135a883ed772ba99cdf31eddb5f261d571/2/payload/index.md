Trust Wallet - Integration with Decred
## Abstract
Trust Wallet is a "fully decentralized wallet" that allows users to store multiple cryptocurrencies.  Trust Wallet was acquired by Binance in August of 2018, originally a simple Ethereum wallet, it has been improved to store a variety of digital assets (and retain custory of your own private keys).

Trust Wallet also employes a native Web3 browser to allow DApp exploration and plans to release custom networks, market monitoring, test networks and a native DEX.

Trust Wallet Core is the cross-platform library that implements low-level cryptographic wallet functionality for all supported blockchains. Most of the code is C++ with a set of strict exported C interfaces. The library provides idiomatic interfaces for all supported languages (currently Swift for iOS and Java for Android).

To facilitate balance lookup, searches, and other functionality without relying on a 3rd party server, Trust Wallet utilizes Blockbook, the back-end service for Trezor wallet.

## Motivation

I believe that as the Decred project continues to scale it is important to integrate functionality for our blockchain with leaders of compatible technology in our shared space. Trust Wallet provides unusually high security and transparency for a mobile wallet, two often noted values in the Decred community. The Blockbook development required for Trust Wallet will also allow for additional integrations with existing Trezor technology and may enable easier integration of Decred in future products.

## Implementation
Implementation will follow the process as detailed in the Trust Wallet document [Adding Support for a New Blockchain](https://github.com/TrustWallet/wallet-core/wiki/Adding-Support-for-a-New-Blockchain).

The two major components of this process are: 

1. Add transaction signing for Decred in the [Wallet Core](https://github.com/TrustWallet/wallet-core) following the [Trust Wallet contribution guide](https://github.com/TrustWallet/wallet-core/blob/master/docs/Contributing.md) (to be completed by the Trust Wallet team).
2. Add backend/node support for Decred to [Blockbook](https://github.com/trezor/blockbook) following the [Blockbook contribution guide](https://github.com/trezor/blockbook/blob/master/CONTRIBUTING.md) (to be completed and hosted by the Decred Project team).

## Contractors
This is request to approve the start of work on Blockbook integration by the Decred Project (developers to be selected from established contributors) and the Wallet Core Development by members of the Trust Wallet Development team.
Note that no funds will be paid from the treasury unless the qualified resources decide to move forward with the work required.

This is a proposal to signal the community would like to be integrated with Trust Wallet and not a guarantee of completion.

## Timeline
Estimated at 2-4 weeks.

## Projected Cost
Line Item | Estimated Hours | Assigned To | Estimated Cost (Paid in DCR)
---       | ---             | ---        | ---
Wallet Core Development | 20 HRS | Trust Wallet | 1200 USD
Blockbook Integation | 30 HRS | Decred Project | 1800 USD
Blockbook Hosting Setup | 5 HRS | Decred Project | 300 USD
Blockbook Hosting | Per Month | Decred Project | 50 USD
Ongoing Development | Per Month | Decred Project | 50 USD

Estimated total integration cost: 3300 USD (Paid in DCR)

Estimated monthly support cost: 100 USD (Paid in DCR)

* Note that the Trust Wallet team has moved forward on their part of integration at no cost to Decred team - [Trust Wallet - Decred Pull Request](https://github.com/TrustWallet/wallet-core/pull/188)