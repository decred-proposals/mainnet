Decentralized Exchange Specification Document

## Abstract

Per the [DEX Infrastructure RFP Proposal](https://proposals.decred.org/proposals/5431da8ff4eda8cdbf8f4f2e08566ffa573464b97ef6d6bae78e749f27800d3a), this is a proposal to “create a full RFC-style specification for the processes described in this proposal prior to code being written”.  The specification document will ensure the DEX operates in a way that:

* minimizes the amount of data sent between clients and servers
* makes the order matching process as fair as reasonably possible
* minimizes the complexity of the design
* handles misbehaving clients appropriately
* allows exchange operators to enforce simple policies for submitted orders
* allows clients to efficiently fetch real-time and historical data

These specifications would be created on a Decred GitHub repository, and the process will be open to external scrutiny and input.

The specifications will not impose specific requirements on the user interface (“UI”) design or functionality since in practicing the principle of "form follows function", it is necessary to fully flesh out function to make reasonable requirements on the UI, e.g. a sensible UI for defining and placing orders likely depends on how the order matching process operates and is actually implemented.

## Motivation

Since there are typically large amount of value involved in the exchange process, it is important to get this as close to correct on a first pass as possible.  Historically, the project has not created a specification for any work we perform in advance of doing the development.  Fixing the exchange process is something that requires getting the details right. As such, a specification should be drafted prior to starting the development process.

## Implementation

To create a proper specification, we will be focusing on:

* order formats
* message formats
* response messages and the circumstances where they occur
* order matching algorithm details
* settlement via atomic swaps
* failure mode handling details
* interaction with blockchain data
* encryption of data in-transit

This information will be laid out in a way to make it straightforward for developers to create an implementation from the specification.

## Contractors

Company 0 LLC, Jon Chappelow (dcrdata), Brian Strafford (dcrdata) and Jamie Holdstock (politeiagui and dcrpool) will complete the work on the specification.  Other contractors can participate as they see fit, subject to approval from Company 0 LLC.

## Timeline

2 months to complete the specification from the approval date for this proposal.

## Projected Cost

It is estimated this work will cost USD 20,000 or less.