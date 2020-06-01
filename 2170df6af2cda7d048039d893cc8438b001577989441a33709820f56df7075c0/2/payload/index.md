Decred Bug Bounty Proposal: Phase 3

# What:

This is a renewal proposal for the decred bug bounty program. The [current](https://proposals.decred.org/proposals/073694ed82d34b2bfff51e35220e8052ad4060899b23bc25791a9383375cae70) program ends on June 30th, 2020.

# Why:

The decred bug bounty program allows us to make use of external talent to find vulnerabilities. Any significant project in the cryptocurrency space needs to have a bug bounty system to be able to process vulnerability reports and to fairly pay the submitter. 

It also provides an incentive for a vulnerability finder to report it to us instead of selling/exploiting the vulnerability or keeping it to themselves. 

# How:

The website bounty.decred.org is the main source of information for bug bounty hunters.

We will have a self-hosted program and use a @decred.org email for getting bug bounty reports. The bug bounty hunters will be sending us PGP encrypted emails of their findings in a predefined format.

Indicative payout amounts:

Note: up to 300 USD

Low: up to 1,000 USD

Medium: up to 3,000 USD

High: up to 10,000 USD

Critical: up to 25,000 USD



The main work that will be undertaken under the proposal.

    Check, validate, and respond to all bug reports sent to the system.

        - If it is a serious vulnerability escalate the vulnerability to the person-in-charge of the project.

        - If it's not a serious vulnerability then open an issue in GitHub and follow through on fixes.

    Maintain constant contact with the bug reporter and keep them apprised on the status of their report.

    Decide on payout amounts.

    Update and maintain the decred bounty website.

Rules and Scope can be found on https://bounty.decred.org/#Scope. This will be edited throughout the program as required.

# Who:


**Validator List:** JoeGruff, Degeri (me), matheusd, jholdstock, fernandoabolafio.

**Website Development:** fernandoabolafio, Degeri (me), jholdstock

### Continuity plan - 

I will be the main person running the day to day and will have access to view all its spending in the CMS system. In the event, I am unable to do so due to some unforeseen circumstances the people above can choose to either shut down the program or have an all contractor vote so that someone can take over until renewal. 

# Costing and Funds:

All contractor work will be logged into the CMS system.

The time spent to validate and write up triaged issues will be taken from the core development budget.

**How the payout process works:- **

```

We actively encourage all submitters to use PGP to encrypt their emails. Once a secure channel has been established all communication is done via PGP.  If the emails are not encrypted then the payout is reduced by 10% this gives the submitter incentives to encrypt their next submission without being excessively punitive. 

Once a vulnerability has been verified as legitimate we get in contact with the developers to work on a fix.

We wait until the bug has been fixed to determine the payout amount since the process of fixing might reveal more bugs and potentially increase the payout. (This might be subject to change if the developers take too long to fix but that's the exception rather than the rule)

Once the patch has been produced/merged the payout is done on the next available treasury payout. It is not fair to make a submitter wait for the 6+ months' time it might take to get a fix to the public for client-side code. 

We always try to coincide the payout with the submission month payouts. (eg: if submitted on June 5th the payout will be the done on July). The dollar average rate will be for the June month. 

The submitter will be invited to the CMS platform on a temporary one-time account (They do not have to pass DCC). The payout will only be in DCR.   The submitter will be given one month to claim the bounty after which it will be considered forfeit.

```

## Budget:

The last proposal spent significantly less than the budget, hence I will be slashing it. I am still leaving some leeway for any surge in emails/ report counts.

Maintaining the bounty website and any updates. (1,500 USD)

Defining policies/rules and scope (1,000 USD)

Any other nonbounty expenditure like emailing, book-keeping, writeups, etc . (2,500 USD) 

##### **Total: 5,000 USD**


Since we cannot predict the types of vulnerabilities and their severity it is not possible to have a fixed payout limit. So I am capping the maximum budget for payouts to be **100,000 USD** for the duration of this program.

#### Breakdown of spendings for the past 10 months (May and June 2020 not included):-

**Website edits:**  590 

**Bookkeeping, Triage and mail correspondence:**  1190

##### Total: **1780**

#### Breakdown of payouts:

[Dcrdata POST based open redirect](https://github.com/decred/dcrdata/pull/1563) : 90

[Politeia Secuity headers fix](https://github.com/decred/politeiagui/pull/1744) : 135

[testnetfaucet race could drain wallet](https://github.com/decred/testnetfaucet/pull/60) : 250

Unreleased "Medium" level vulnerability: 3000 

##### Total payouts: **3475**


### Breakdown of submitters:

*Since July 1, 2019 *

Total submissions: **60**

Total Unique email ID's: **36**



# When and Duration:

This project will be approved for **1 year** (July 1, 2020 - June 30, 2021) or until the bounty/operating funds have been depleted.