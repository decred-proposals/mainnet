Decred ATM Integration - Approval for Planning Phase
# ATM Integration - Approval for Planning Phase
## Abstract
ATMs would be an accessible means to exchange cash for Decred purchase and usage when combined with a mobile wallet.  As Decred continues to develop into a preferred alternate SoV the geographical convenience of crypto ATMs extend many of the benefits local physical currency embodies.

## Motivation
The ability to move from fiat into Decred is a friction point for all interested community members.  With the creation of mobile wallets, the Decred project can now leverage the existing ATM infrastructure deployed for Bitcoin by integrating Decred purchasing directly into the open source repositories of ATM manufacturers.
Positive sentiment towards ATMs as a means to acquire Decred was shared on a prior proposal along with concerns about price and impact.  During the proposal community initiated research into options which would create greater impact for Decred (more value).
The basic information regarding the top manufacturers and their integration process:

Manufacturer  | Machine Count | Mapped Locations | Integration Offered | Marketing Offered | Deployment Type | Development Type | Repo Location
 ---          | ---           | ---              | ---                 | ---               | ---             | ---              | ---
Genesis Coin  | 2000+         | 1382             | No                  | N/A               | N/A             | Unknown          | N/A
General Bytes | 2000+         | 1294             | Yes                 | Yes               | Push            | Open Source      | https://github.com/GENERALBYTESCOM
Lamassu       | 1000+         | 445              | Yes                 | Yes               | Pull            | Open Source      | https://github.com/lamassu
BitAccess     | 300+          | 246              | Yes                 | No                | TBD             | Open Source      | https://github.com/bitaccess
Coinsource    | 200+          | 186              | No                  | N/A               | N/A             | Unknown          | N/A

To contibute or comment on this specific information, use the following gist:
https://gist.github.com/oregonisaac/2fce4a327f7d8067e34791a8c2eb9536

## Implementation
Based on the research and discussions with ATM producers to date, as the basics of which are illustrated in the above gist, General Byte has thus far been the largest ATM producer with an amiable integration process.  The following implementation steps assume utilizing General Bytes.  For a map of General Bytes ATM locations and to determine if there is an operator with General Bytes machines in your area see CoinATMRadar: https://coinatmradar.com/manufacturer/5/general-bytes-bitcoin-atm-producer/

### Initiation Phase
0. This proposal - signal to start Planning Phase only.
### Planning Phase
1. Confirm agreement with General Bytes to push software at no cost and participate in an optional co-marketing campaign when push is complete.
2. Make an agreement with one of the recommended exchanges General Bytes uses for other cryptocurrencies they currently offer (so that there will be no DCR deposit requirement for ATM Operators).
3. Select a Java Developer/Dev Team to complete the wallet/exchange integration for Decred on General Bytes.  
4. Select “beta machines” close to known Decred community for early software push and testing.
5. Initiate second Politeia proposal with specific contractor and budget information for approval.
### Development Phase
6. Develop the wallet software by cloning the open source General Bytes coin repo (Java) and integrating.
7. Push software to beta machines and perform test purchases and sales on machines local to Decred community willing to participate in beta.  Capture any issues and errors and correct as required.
8. Create screen captures and generate walk through instructions for the team and Decred Docs.
9. Prepare co-marketing campaign with Ditto PR and General Bytes CMO.
### Execution Phase
10. Push Decred software to all General Bytes machines.
11. Market to General Bytes ATM operators and ask for location list of machines willing to activate Decred on their ATMs.
12. Validate list with ATM Operators.
13. Create known ATMs list on Decred.org.
14. Initiate co-marketing targeting locations with known ATMs.
### Control/Closure
15. Monitor support channels for ATM issues.
16. Handle escalations to General Bytes and/or Development and perform RCA.

## Contractors
This is request to approve the start of the RFP (Request For Proposal) process, where we are assessing stakeholder sentiment before soliciting any bids to complete this work. If this proposal passes, contractors will be chosen at a later date, per stakeholder preference.  A second proposal will then be offered to the community to approve the contractors selected and budget.

## Timeline
Estimated at 3-6 months.

## Projected Cost
### This Proposal
Estimated the planning work will cost between USD 600 and 1000 to complete.
### Full Project
The subsequent phases (second proposal required) are roughly estimated cost between USD 10000 and 20000 to complete.