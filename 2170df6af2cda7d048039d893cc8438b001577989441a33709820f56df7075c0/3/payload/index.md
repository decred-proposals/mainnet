Decred Bug Bounty Program: Phase 3

## What

This is a renewal proposal for the Decred Bug Bounty program. The current [Phase 2](https://proposals.decred.org/proposals/073694ed82d34b2bfff51e35220e8052ad4060899b23bc25791a9383375cae70) program ends on June 30th, 2020.

## Why

The Decred Bug Bounty program allows us to make use of external talent to find vulnerabilities. Any significant project in the cryptocurrency space needs to have a bug bounty system to be able to process vulnerability reports and to fairly pay the submitters.

It also provides an incentive for a vulnerability finder to report it to us instead of selling/exploiting the vulnerability or keeping it to themselves.

## How

The website [bounty.decred.org](https://bounty.decred.org/) is the main source of information for bug bounty hunters.

We will have a self-hosted program and use a @decred.org email for getting bug bounty reports. The bug bounty hunters will be sending us PGP encrypted emails of their findings in a predefined format.

Indicative payout amounts:

- Note: up to $300
- Low: up to $1,000
- Medium: up to $3,000
- High: up to $10,000
- Critical: up to $25,000

The main work that will be undertaken under the proposal:

1. Check, validate, and respond to all bug reports sent to the system.

   - If it is a serious vulnerability, escalate the vulnerability to the person-in-charge of the project.
   - If it's not a serious vulnerability, then open an issue on GitHub and follow through on fixes.

2. Maintain constant contact with the bug reporter and keep them apprised on the status of their report.

3. Decide on payout amounts.

4. Update and maintain the Decred Bug Bounty website.

Rules and Scope can be found at [bounty.decred.org/#Scope](https://bounty.decred.org/#Scope). This will be edited throughout the program as required.

## Who

**Validators:** Degeri (me), fernandoabolafio, jholdstock, JoeGruff, matheusd

**Website development:** Degeri (me), fernandoabolafio, jholdstock

### Continuity plan

I will be the main person running the day to day operations of the program and will have access to view all its spending in the Contractor Management System (CMS). In the event I am unable to do so due to some unforeseen circumstances, the people listed above can choose to either shut down the program or have an all-contractor vote so that someone can take over until the renewal.

## Costs and funds

All contractor work will be logged into the CMS system.

The time spent to validate and write up triaged issues will be taken from the core development budget.

**How the payout process works:**

- We actively encourage all submitters to use PGP to encrypt their emails. Once a secure channel has been established all communication is done via PGP. If the emails are not encrypted then the payout is reduced by 10%. This gives the submitter an incentive to encrypt their next submission without being excessively punitive.

- Once a vulnerability has been verified as legitimate we get in contact with the developers to work on a fix.

- We wait until the bug has been fixed to determine the payout amount since the process of fixing might reveal more bugs and potentially increase the payout. (This might be subject to change if the developers take too long to fix but that's the exception rather than the rule)

- Once the patch has been produced/merged the payout is done on the next available treasury payout. It is not fair to make a submitter wait for the 6+ months' time it might take to get a fix to the publiс with the next release of Decred [binaries](https://github.com/decred/decred-binaries).

- We always try to coincide the payout with the submission month payouts. For example: if submitted on June 5th the payout will be the done in July, and the dollar average rate will be for the month of June.

- The submitter will be invited to the CMS platform on a temporary one-time account (they do not have to acquire the Decred Contractor Clearance, DCC). The payout will only be in DCR. The submitter will be given one month to claim the bounty after which it will be considered forfeit.

### Budget

The last proposal spent significantly less than the budget, hence I will be slashing it. I am still leaving some leeway for any surge in emails/report counts.

- Maintaining the bounty website and any updates: $1,500
- Defining policies/rules and scope: $1,000
- Any other non-bounty expenditure like emailing, bookkeeping, writeups, etc.: $2,500

**Total: USD 5,000**

Since we cannot predict the types of vulnerabilities and their severity it is not possible to have a fixed payout limit. So I am capping the maximum budget for payouts to be **USD 100,000** for the duration of this program.

## Phase 2 review

Breakdown of spendings for July 1, 2019 - April 30, 2020 (May and June not paid yet):

- Website edits: $590
- Bookkeeping, triage and mail correspondence: $1,190
- **Total spendings: USD 1,780**

Breakdown of payouts (July 1, 2019 - May 31, 2020):

- dcrdata: [POST-based open redirect](https://github.com/decred/dcrdata/pull/1563): $90
- Politeia: [secuity headers fix](https://github.com/decred/politeiagui/pull/1744): $135
- testnetfaucet: [race could drain the wallet](https://github.com/decred/testnetfaucet/pull/60): $250
- Unreleased "Medium" level vulnerability: $3,000
- **Total payouts: USD 3,475**

Breakdown of submissions (July 1, 2019 - May 31, 2020):

- Total submissions: **60**
- Total unique email IDs: **36**

## When and duration

This project will be approved for **1 year** (July 1, 2020 - June 30, 2021) or until the bounty/operating funds have been depleted.
