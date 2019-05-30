Block Header Commitments Consensus Change

# Proposal Structure

Since this is a highly technical proposal that ultimately involves consensus rule changes, it has been split into two main sections:

- General Audience
- Technical Details

The general audience section aims to provide a high-level overview of the proposal along with other details most suitable for all stakeholders, including those who are not developers or are otherwise unfamiliar with the inner workings of consensus.

On the other hand, the technical details section contains a more in-depth discussion of the relevant technical aspects, implementation specifics, and rationale for the chosen semantics of the proposal.

# General Audience

## High-Level Overview

The primary goal of this proposal is to increase the security and efficiency of lightweight clients, such as Decrediton in its lightweight mode and the dcrandroid mobile wallet, as well as add infrastructure that paves the way for several future scalability enhancements.

It accomplishes this by carefully repurposing certain fields in the block header in a way that avoids breaking existing mining hardware while still allowing the necessary information to be made available to the aforementioned lightweight/mobile clients.  It also includes some optimizations to the underlying mechanisms the clients depend on to function.

## Why Focus on Increasing Security and Performance of Lightweight Clients?

Three extremely important goals of the Decred network are to:

- Avoid centralized points of failure through decentralization
- Provide a high degree of security
- Eliminate, or at least significantly minimize, trust in 3rd parties

These goals extend to mobile wallets and devices as well.  As such, they ideally need to remain decentralized, trustless, and provide nearly the same security as wallets that perform full validation.

Strong support for secure and efficient mobile wallets will help increase Decred's accessibility as a Medium of Exchange (MoE) to complement its existing excellent Store of Value (SoV) characteristics.

Unfortunately, mobile devices typically have significantly fewer resources available than the predominant hardware currently running Decred wallets which effectively precludes them from performing the exact same level of full validation that provides the most security and zero trust.  Due to these constraints, mobile wallets must rely on alternate validation mechanisms.

In short, the current available mechanisms for mobile wallets force them to choose between two less than ideal options:

1. Remain decentralized and nearly trustless at the cost of notably weaker security
2. Completely trust a centralized server controlled by the wallet vendor to accurately deliver the transaction information

Notice that the first option is close to having the aforementioned ideal properties, except for the shortcoming of having notably weaker security.  Thus, by increasing the security of the mechanism used by lightweight clients in the first option, which include mobile wallets and devices, to nearly match that of full validation, all of the ideal properties can be achieved.

## Consensus Rule Change Cost Benefit Analysis

When considering changes to the consensus rules, it is paramount to examine both the positive and negative consequences of the proposed changes as there are nearly always tradeoffs involved in one form or another.  The following two sections provide an analysis in the form of pros and cons accordingly.

### Pros

- Increases lightweight client security to nearly match fully-validating node security
- Reduces the overall resource requirements for lightweight clients during operation
- Reduces the amount of time it takes lightweight clients to synchronize
- Does not require Proof of Work miners to make any changes to their pool software or break existing hardware thereby reducing possible disruption to the ecosystem
- Enables several future scalability enhancements without sacrificing security

### Cons

- Wallets that make use of lightweight mode will need to be updated to accommodate the proposed changes
- All fully-validating nodes will be required to provide support for the proposed changes versus the current optional lower security scheme

## Who Will Complete the Work?

This work will primarily be completed by Company 0, LLC.  It will also indirectly involve some additional minimal integration work by maintainers of lightweight wallets such as dcrandroid.

## Timeline

The estimated time to complete the necessary code changes described herein, enable the required on-chain vote for consensus rule changes, and produce the relevant technical documentation is in the range of 4 to 5 weeks.

In addition, successful on-chain votes take a minimum of 3 months to fully activate, so the total estimated time to fully deployed code is a minimum of around 4 and 1/2 months.

## License Considerations

All code will be open source and use the same license as the existing Decred software it modifies.

## Projected Cost and Payment Details

This proposal will require both a consensus and wallet expert at minimum to complete.  The costs are projected to be USD 20,000.  These funds will be drawn from the core network development budget.

# Technical Details

## Abstract

This proposes modifications to the Decred block header to provide an extensible framework, via future consensus-voted hard forks, for adding consensus-enforced commitments to the header without requiring any changes to its size or mining-related field offsets along with an initial commitment to an updated and optimized version of GCS (Golomb-coded set) filters.

## Motivation

Currently, the only fully-supported trustless security model in Decred is the full-node model where every node and wallet is required to have access to the entire blockchain to verify every block faithfully follows all of consensus validation rules.

While this model provides the highest security guarantees and is required by the consensus daemon to provide an ordered and timestamped public ledger that protects against double spends and modification of existing transactions, it is highly desirable to support other security models where applications can make varying levels of security tradeoffs according to their domain in exchange for no longer requiring access to whole blocks or the entire blockchain.

### Simplified Payment Verification (SPV)

One well-known alternative security model is SPV.  This model supports verifying payments without requiring access to the entire blockchain in exchange for trusting proof-of-work and proof-of-stake miners to verify the history and a stronger non-partitioning assumption.  However, this means that if an attacker is able to overpower the network, it can trick SPV nodes into believing fabricated transactions are valid for as long as the attacker overpowers the network.

In addition to all potential avenues for fraud typical to pure proof-of-work systems, Decred's hybrid proof-of-work and proof-of-stake model adds additional considerations such as consensus voting results, ticket selection semantics, and block invalidation.  Another complication with this model is that it relies on the ability to identify and retrieve relevant transactions which can be challenging to do without leaking information regarding coin ownership, which is not ideal from a privacy perspective.

Nevertheless, it is possible to bring the SPV security level very close to that of full nodes through a combination of committed fraud proofs, inclusion proofs, and filters so long as there is at least one honest fully-validating node on the network to sound the alarm.  This is the case because once it is possible to generate a compact fraud proof which SPV nodes can verify quickly, they can securely reject the associated invalid block(s) accordingly.

Compare this model to the completely trust-based model many lightweight and mobile wallets use today where they communicate with a centralized server controlled by the wallet vendor and simply trust everything the service reports.

### Alternative Security Models

There are also a variety of other security models with varying levels of tradeoffs that can be achieved by making commitments which allow compact proofs that can be verified quickly readily available.  A couple of examples are history pruning with full validation starting from the first non-pruned block, and selective proofing.

With careful design, applications can make use of relevant committed proofs to offer strong cryptographic guarantees of certain aspects without needing to fully validate the entire chain themselves.  Such models are typically highly preferable to the fully trust-based models that most applications use at the current time.

## Specification Caveats

This proposal provides an informal specification which describes the high-level changes with sufficient detail for a knowledgeable consensus and wallet engineer to implement it.  The final result is expected to be close to the specification provided herein, however, consensus rule changes are notoriously detail-oriented and fraught with unexpected corner cases.  Further, the fine-grained details, such as the specific optimal GCS filter parameters, have intentionally been omitted as they will require an in-depth analysis as a part of the implementation process.  Consequently, this informal specification is subject to minor changes that might ultimately be necessary as determined during the engineering process.

In any case, since this proposal will ultimately result in changes to the consensus rules, a [DCP](https://github.com/decred/dcps/) with the final full technical specification, additional details such as a description of fraud and inclusion proofs, discussion of other designs considered, deployment specifics, and test vectors will be required as a part of the on-chain voting process.

Finally, the on-chain vote provides stakeholders with an opportunity to reject the final result if it were to ultimately end up deviating from this informal specification in some way the stakeholders deem unacceptable.

## Informal Specification

- Repurpose the `StakeRoot` field to house a commitment root and rename it to `CommitmentRoot` accordingly
- Calculate the new `CommitmentRoot` field as the root of a Merkle tree whose leaves are the individual hashes for each desired commitment
  - Introduce a new commitment to a version 2 compact GCS filter for the block 
- Modify the existing `MerkleRoot` field to include the stake transactions in addition to the regular transactions to ensure the header still commits to them by calculating it as `BLAKE256(regular_tx_tree_merkle_root || stake_tx_tree_merkle_root)`
  - Note that this is simply itself a two-leaf Merkle tree that consists of the two Merkle roots of the respective transaction trees
- Introduce a new filter type `GCSFilterRegularV2` that includes several optimizations
  - Commit to previous output scripts instead of previous outpoints
  - Modify the filter parameters such that `P` and `M` are optimal for Decred
  - Replace the modular reduction with an optimized fast range mapping
- Update the `cftypes` p2p protocol message to include reporting the new filter type
- Modify the `cfilter` p2p protocol message to recognize and serve the new filter type
- Alter the `cfilter` p2p protocol message to include a Merkle proof which allows the client to prove the inclusion of the GCS filter in the new `CommitmentRoot` header field once it becomes available
  - The proof must only be provided for the new filter type `GCSFilterRegularV2`
- Support proofs against filters for blocks prior to the activation of the new filter commitments
- Bump the wire protocol version

## Rationale

The most efficient and convenient location to store consensus-enforced commitments which allow compact proofs to be generated is the block header.  Additionally, most software which works with the blockchain nearly always already requires access to the block headers in order to follow the chain with the most proof-of-work and prove transactions are included in the associated block by making use of the committed Merkle root.  Further, since headers are already an integral part of the system, there is already significant tooling for acquiring and working with them.

The proposed changes are intentionally engineered to avoid changing the overall size of the header and field offsets of all mining-related fields to prevent breaking existing mining hardware and infrastructure that secures the network.

The `StakeRoot` field was repurposed to house the new commitment scheme since it is already the correct size for a commitment Merkle root hash and the stake transaction tree Merkle root can be rolled into the existing `MerkleRoot` field elegantly without requiring significant modifications.

Making use of a Merkle tree for calculating the new `CommitmentRoot` field allows efficient log-sized inclusion proofs of the commitments to be generated and requested from untrusted sources.  Further, each leaf is itself intended to be a commitment to some arbitrary data which will typically be some structure that employs techniques that also allow compact fraud and inclusion proofs to be constructed such as Fenwick trees, Golomb-Rice filters, and additional Merkle trees.

This approach provides an extensible and efficient method of consensus-enforced proof chaining which allows the block header to commit to an arbitrary number of short proofs which thin clients can very quickly verify.

An initial commitment to the GCS filters necessary to securely support lightweight clients has been included as a part of this proposal to immediately make use of the new infrastructure without requiring a several month voting period first.

Finally, once the GCS filters are committed to via the new `CommitmentRoot` field, their specific implementation characteristics will necessarily become a part of the consensus rules. Therefore, this proposal also includes several optimizations to the existing non-consensus-enforced filters in order to avoid the need for another future vote to incorporate them.