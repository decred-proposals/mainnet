Decentralized Exchange Development

## The Decred Distributed Exchange (DEX)

Let's build the DEX!

In March, stakeholders overwhelmingly [approved](https://proposals.decred.org/proposals/5431da8ff4eda8cdbf8f4f2e08566ffa573464b97ef6d6bae78e749f27800d3a) a request for proposals (RFP) for a novel type of decentralized exchange (DEX). 
The Decred DEX is a powerful vision of returning power to the people with a trustless trade process designed to cut out the bots, the middlemen, and the centralized power.

In June, you [approved](https://proposals.decred.org/proposals/a4f2a91c8589b2e5a955798d6c0f4f77f2eec13b62063c5f4102c21913dcaf32) the first step towards actualization, resulting in publication of the [DEX specification](https://github.com/decred/dcrdex) and setting a clear path forward for open and active development.

It's time to turn words into action. 
Here's our plan to develop the DEX, for your approval.

### Executive Summary

The Decred DEX enables trading of one type of digital asset for another.
While this may seem like a problem that has already been solved, current solutions have intentional or unintentional features which introduce risk and encourage market manipulation.
Most trading is performed on centralized exchanges, where users entrust all control of their funds to the exchange operator.
This creates high-value targets for hackers and exit scammers, resulting in the [theft of at least USD 1 billion](https://www.cnbc.com/2018/06/07/1-point-1b-in-cryptocurrency-was-stolen-this-year-and-it-was-easy-to-do.html) worth of cryptocurrencies in just the first 5 months of 2018.

The Decred DEX solves this problem by enabling people to trade directly with each other, without risk of losing funds, using a special type of contract published directly to the blockchains.
The DEX itself acts only as a match maker and communication relay, never holding any funds or collecting any trading fees.
This decentralized model includes additional features to foster a healthy community of traders while stripping power from malicious actors.

The benefits to Decred are numerous.
Everybody wins when Decred is more accessible and with lower risk, and Decred once again asserts itself as a leader of decentralized finance technology.

This proposal is for the work of implementing the DEX and a reference client.
Development will be led by experienced Decred developers but open to contributions from all, following the established Decred open-source contractor model.

### Projected Cost

It is estimated this work will be completed at a cost of approximately USD 230,000. The vast majority of the costs are expected to go towards labor, with minor computing resource costs at later stages. Funds will be drawn from the treasury as monthly contractor payments under a new contractor management system (CMS) subdomain. Any overage would require stakeholder approval via proposal.

## Technical details

This section will give technical details related to the processes and products of this work. 
For an in-depth technical overview of the trade protocol, see the [DEX specification](https://github.com/decred/dcrdex).

### Deliverables

Below is a high-level overview of the major components. A more nuanced picture can be found [here](https://gist.github.com/chappjc/20e33c864e81dc64ba8b1e626dedfd1f), which is subject to revision.

**DEX Server**

The DEX server will be a command-line interface (CLI) program written in Go.
The server can be roughly divided into the following sub-components. 

- **Communications hub**: Handle websocket connections. Relay messages. 
- **Account manager**: Registers new clients and validates payment of registration fees.
- **Exchange**: Coordinate markets and order books. Perform order matching. 
- **Swap coordinator**: Track matches. Monitor community conduct.
- **Archivist**: Store and retrieve historical order information.

**DEX client**

The DEX client developed in this work will be a command-line interface (CLI) application.
However, future development projects will implement a client with a graphical user interface (GUI) using the Electron Framework.
The initial client implementation will require a full node (e.g dcrd and btcd) and native wallet software, with which the client will communicate via RPC.
The client will comprise the following major components.

- **Connection manager**: Open and close DEX connection. Route messages.
- **Wallet manager**: Query UTXOs. Create, sign, and broadcast transactions.
- **Order book sync**: Download order books and keep them synchronized.
- **User interface**: Registration, charts and tables, order placement, order history.
- **Order manager**: Handle matches. Initialize subsequent atomic swap steps.

### Major Milestones

The most significant milestones, which may proceed in parallel, are:

- Coding and test coverage of **core server modules**: order matcher, swap coordinator, order book manager, the common asset interface, two or more asset backends, and the client communications hub.
- Coding and test coverage of **high level server modules**, the archivist and database backend for user and historical data storage and retrieval, the account manager, and the market manager (employs the matching, swap, and book modules).
- Server **systems integration**, and development of the DEX controller and administrative portal.
- Client core modules.
- Client command line application.
- Wallet modifications to facilitate UTXO locking and other swap related changes.
- (possible) Simple web interface to the client, primarily to aid manual testing of the client.
- Full unit and system integration tests.

### Development Plan

This work will be led by Jonathan Chappelow (@chappjc) and Brian Stafford (@buck54321) along with Company 0 LCC, but the DEX is open-source and anyone may contribute. Approved Decred contractors will be compensated for their work.

The server and reference CLI client will be written in Go.
Work will be coordinated through a public GitHub repository.
Because the API specification is already written, server and client work can be performed largely in parallel.
All tasks will be associated with a GitHub issue assigned to a developer. This method encourages community input from the planning stage and enables use of additional developer tools, e.g. GitHub projects. 

While recognizing the value of having a diversity of programming styles, we will generally encourage a test-driven development approach, working on and testing individual core modules before plugging everything into a larger framework.
This approach emphasizes modularity, resulting in more flexible and testable code and facilitating a good team workflow.

A minimum of semi-monthly project updates will be broadcast through social channels, highlighting development milestones and setbacks. 
