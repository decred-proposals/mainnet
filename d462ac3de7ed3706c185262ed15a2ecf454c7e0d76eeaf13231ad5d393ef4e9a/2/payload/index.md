Decred DEX Development Phase II

# Decred DEX Development - Phase II

In August of 2019, stakeholders [approved](https://proposals.decred.org/proposals/417607a) the development of the Decred Decentralized Exchange (DEX).
Since then, we've been hammering at our keyboards making DEX a reality.
After months of intensive testing, the DCRDEX software [was officially released](https://github.com/decred/dcrdex/releases/tag/release-v0.1.0) in October 2020, and already tens of thousands of DCR are traded daily - directly between users and with no third-party custody - using the released DCRDEX software built in Phase I; volume on par with Binance and Bittrex.
Due in no small part to the push of Decred's social media influencers, interest remains high and DEX is seeing new active users every day.

Now that we've got a basic product working, it's time to take Decred DEX to the next level.
Work thus far has been focused on implementing a core trading protocol and basic interface, but our next push is all about growing patronage and improving user experience.
**Easier setup and more assets** is the name of the game now, because easier, faster on-boarding is critical to reaching a wider audience, and every new asset we add exposes DEX (and Decred) to a new community.

We've collected feedback from all over the Decred-sphere, and the plans below are intended to address the most common requests and concerns, and to deliver the best value for our development DCR.
The next stage of development will make DEX more accessible and increase its utility, and we could not be more excited to get started.
We hope you'll allow us to guide DEX into the next era.

## Executive Summary

Work on DEX so far has been aimed at creating a **minimum viable product (MVP)**. MVPs are functional but bare-bones.
The DEX software has 3 working assets, and running DEX requires significant and sometimes difficult setup. 

In order to make DEX easier to use, we are going to work on eliminating the full-node requirement, and streamlining DEX client setup.
We plan to support SPV wallet modes, eliminating the need to run dcrd and bitcoind separately from the DEX software.

In order to attract a wider audience, we're going to add support for more assets. Our primary target is Ethereum and ERC20 tokens, including stablecoins.
Stablecoins are a popular trader's tool and also grant us the ability to display crypto-to-fiat exchange rates for the user.
Additionally, we plan to add support for more Bitcoin forks, since our modular clone backends make these relatively easy to do.

## Development Objectives

To narrow down the list of objectives, we applied the following filters.

- Does completion of the objective satisfy some commonly expressed desire in the Decred or wider blockchain community?
- Are we confident that we posses the skill and resources to accomplish the objective?
- After weighing the costs and benefits, is completion of the objective a good return on the investment?

### Smoother On-boarding

There are three key ways we plan to improve the DEX user experience:

1. **SPV (Simplified Payment Verification)** wallet support will enable quick startup and greatly reduced disk space usage. Presently, the DEX client (dexc) requires that both Decred and Bitcoin wallets operate with full nodes whereby the entire blockchains must be downloaded to the user's computer. With Decred's existing SPV wallet functionality, and [Bitcoin Core's recently-completed compact filters SPV implementation](https://github.com/bitcoin/bitcoin/pull/18876) we can allow DEX users to run both of these wallets without a full node. The drastically reduced resource requirements will open up DEX to a much broader user base.

 There is still some question of the best way to handle Bitcoin, which has limited network support for the new compact filters SPV (there is not yet a released version of Bitcoin Core that signals compact filters support on the Bitcoin network), but there are multiple viable paths including Decred-operated reference Bitcoin nodes with the necessary features enabled for DEX clients while these features become more widespread.

2. **Support Decrediton integration efforts.** A frequent question is if or when DEX will be "integrated" with Decrediton. In general terms, this means Decrediton managing dexc, and dexc using Decrediton's wallet: starting and stopping dexc as requested by the user, hiding the dexc command line as Decrediton presently does for dcrwallet, at least partially automating the initial setup of dexc, and providing the trading interface in a dedicated window rather than a browser. Most of these tasks are necessarily work for the Decrediton development team, but we will support those efforts as needed. For instance, we anticipate a number of changes to dexc to facilitate the supervisory role of Decrediton.

### More Markets

3. **Ethereum support** is a one-time implementation that not only allows ETH swaps, but gives us access to countless other assets built with Ethereum's [ERC-20 token standard](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/). This includes stablecoins such as USDC and USDT, which are an important trader's tool and also enable fiat indices without an oracle. We'll commit to getting ETH and USDC ready, but once you have one ERC-20 token, you've pretty much got them all.

 This is a major project given the fundamental differences between Ethereum and UTXO-based assets such as Decred and Bitcoin. However, not only have there been proof-of-concept ETH atomic swaps, there is an [existing Go implementation developed for Decred's atomicswap tools](https://github.com/decred/atomicswap/pull/76) and [Go Ethereum libraries](https://github.com/ethereum/go-ethereum) that can be leveraged to get this functionality into DEX.

4. Many **Bitcoin forks** are relatively easy to implement. We've built a BTC-clone framework for implementing BTC-like assets such as Litecoin that should allow implementation of many more assets with as few as a couple hundred lines of code. While we hope that non-Decred asset developers will step up and write the code, we can also get a handful of assets up ourselves with limited effort. We will leverage the framework we have developed to add at least one other Bitcoin-like asset, beginning with Bitcoin Cash (BCH). While BCH brings some challenges such as a [new address format (Cash Addr)](https://github.com/bitcoincashorg/bitcoincash.org/blob/master/spec/cashaddr.md) that is based on bech32 but with no segwit transactions, which does not work out-of-the-box with our Bitcoin clone framework, we believe it will be relatively straightforward.

### Continuing Development

The initial release of DEX was fully functional and stable now, but as with any software, especially one as complex as DCRDEX, there is much to be done to maintain and improve the product.  In particular, we intend to continue general development and improvements to both the backend (under-the-hood) and UI aspects of DCRDEX.

5. **General development and product improvement**. This is a somewhat ill-defined category because 1) the most important improvements are often based on user feedback, and we can't predict that at proposal-time, and 2) bug fixes can take up significant time and are obviously hard to predict. We ask for some latitude for on-the-fly decisions on general product improvement, not including any major undertakings or protocol changes. This category covers costs associated with ongoing maintenance, existing issues, security upgrades, support, etc.

 A component of this development bucket is beginning the necessary architectural changes to facilitate DEX server scalability and decentralization, namely, the plan to implement a decentralized DCRDEX network a.k.a. "server mesh". While a full peer-to-peer DCRDEX network is a large undertaking with theoretical prerequisites that need to be explored prior to development, we need to take steps toward better decentralization, scalability, and availability of the server software.
 
 Secondary to preliminary server mesh work is a concept for a built-in Decred wallet, which would reduce runtime dependencies, smooth out initial Decred wallet setup, and make DEX client operation more robust. However, this would be a minimally functional wallet, e.g. lacking all of Decred's governance features, and thus would only be a bridge into the Decred ecosystem. While most new users would be encourage to use Decrediton after DEX integration, some users will prefer to have one less process and may thus be interested in such a built-in Decred wallet mode to accelerate their DEX setup. It also remains to be seen how much of a maintenance and support burden such a feature would create. As such, this concept is not a primary deliverable, but it is something the team is keen to investigate. Work on this would only begin after the highest priority work is addressed.

6. **UI/UX improvement**. We have a few specific user-facing features in mind that we would like to pursue. These will be addressed *as time permits*:

   - **Market history charts and tables**. The current dexc browser interface provides the basics for trading with a transparent order book, but we can also provide the client price charts and trade history.
   - **Simple "instant exchange" interface** option. For users who may not want all the knobs and charts of an order-driven exchange interface that dexc currently provided, a simplified ShapeShift-style instant exchange interface option can be designed.
   - **Order-time options** would allow users to choose between options that affect their on-chain fees at the time of ordering.

## Development Plan and Projected Costs

As with Phase I, the deliverables are entirely open-source software.
This development work will be led by Jonathan Chappelow (@chappjc) and Brian Stafford (@buck54321), and supported by other established DEX developers including: @itswisdomagain, @JoeGruffins, Amir Massarwa (@amassarwi), et al.
The [DCRDEX project](https://github.com/decred/dcrdex) is open-source and contributions are welcomed from approved Decred contractors.
Learn about the [Decred Contractor Clearance (DCC) process](https://docs.decred.org/contributing/overview/#becoming-a-paid-contractor) for more information.

With several developers working in parallel, each allocating a different proportion of their time to the project, effort estimates are given in terms of **FTE (full-time equivalent) weeks** of work.

**NOTE: Effort estimates account for a comprehensive product development process through design, development, systems integration and testing, product validation (via community and internal testing), and release engineering.**
This is because in reality, just churning out some code for the new features gets us about half way; we intend to deliver a complete and well-tested product.
However, there may be one or more product releases depending on the completion of the primary deliverables.
For example, there may be a release for SPV features and BCH support, followed by another release for ETH.

Effort (not calendar) estimates for the primary initiatives roughly break down as follows:

| Initiative                          | FTE Weeks  | Notes                                          |
|-------------------------------------|-----------:|------------------------------------------------|
| 1. SPV                              |         18 |                                                |
| 2. Decrediton integration support   |          6 |                                                |
| 3. ETH and ERC20                    |         26 |                                                |
| 4. BCH++                            |         10 |                                                |
| 5. & 6. Cont. Dev. and Improvement  |         42 | ~9 months of support at 100% FTE effort        |
| **Total**                           |        102 | i.e. 4080 "standard" FTE hours                 |

Given a combined sustained effort corresponding to 3-4 full-time _effective_ developers, **delivery is estimated in 6-9 months**.
Work will begin on SPV and ETH in parallel. Continued Development, which includes support and maintenance and other necessary development, will be ongoing and uninterrupted.

It is estimated this work will be completed at a cost of up to USD 245,000. Funds will be drawn from the treasury as monthly contractor payouts under the Contractor Management System (CMS).

Work will be coordinated through the [dcrdex GitHub repository](https://github.com/decred/dcrdex), with lively discussion as always on Matrix in the [DCR DEX](https://matrix.to/#/!mlRZqBtfWHrcmgdTWB:decred.org?via=decred.org&via=matrix.org&via=planetdecred.org) 
and the [DEX Development](https://matrix.to/#/!SFRQQFIHUUNXARfvew:decred.org?via=decred.org&via=matrix.org&via=planetdecred.org) rooms.

## The initiatives that didn't make the cut

There is a lot of work on the horizon. We've done our best to prioritize work and limit scope for this proposal.
Due to high demand, it's worth mentioning a couple of initiatives that didn't make the cut.
We hope this inspires some discussion and gives some insight into where we think things are headed.

- **Monero compatibility/alternative swap protocol**. [Recent](https://eprint.iacr.org/2020/1126.pdf) [work](https://medium.com/comit-network/monero-bitcoin-atomic-swap-1cab015d7af9) towards [developing a BTC-XMR atomic swap process](https://ccs.getmonero.org/proposals/h4sh3d-atomic-swap-implementation.html) is promising, and we believe it is now possible to implement cross-chain swaps with XMR. Unfortunately, an alternative swap protocol would require substantial rewriting of most components of DEX, and how useful it would be for other assets is questionable. We're putting this one on the back burner for now, but our curiosity remains piqued.
- **Lightning Network** will allow instant settlement and arbitrary lot sizes. We believe that Decred's Lightning Network has a bright future. This is an enormous undertaking that is worthy of its own proposal though, so we're punting for now.
- A **Server Mesh** will take decentralization to the next level. We think this is really, really important, and it will continue to be a major consideration in all of our design decisions, but we're not quite ready to kick off work here yet. However, as mentioned in the Continuing Development initiative, we intend to begin paving the way for this work.
