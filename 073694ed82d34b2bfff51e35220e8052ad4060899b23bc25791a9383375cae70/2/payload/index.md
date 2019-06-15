Decred Bug Bounty Proposal: Phase 2


# What:

This proposal aims to renew the bug bounty program. The current [program](https://proposals.decred.org/proposals/d33a2667469b56942adf42453def6cc2292325251e4cf791e806939ea9efc9e1) ends on June 30th

# Why:

The reasons for having a bug bounty program remain the same. In the first half of this year, we have seen many projects, exchanges and wallets getting compromised. As the cryptocurrency market keeps growing this trend will only continue.

A bug bounty program gives us an extra edge in security. It allows for an outsider to evaluate our security and get rewarded for finding vulnerabilities.


# How:

The website [bounty.decred.org](https://bounty.decred.org/) is the main source of information for bug bounty hunters.

We will have a self-hosted program and use a @decred.org email for getting bug bounty reports. The bug bounty hunters will be sending us PGP encrypted emails of their findings in a predefined format.

We will be using the OWASP Risk Rating Methodology for scoring and prioritizing vulnerabilities (https://www.owasp.org/index.php/OWASP_Risk_Rating_Methodology)

### Indicative payout amounts:

Note: up to 300 USD

Low: up to 1,000 USD

Medium: up to 3,000 USD

High: up to 10,000 USD

Critical: up to 25,000 USD

To achieve all this we need a group of "vulnerability validators" who are existing decred contractors. Their jobs are as follows.

- Check, validate and respond to all bug reports sent to the system.

- If its a serious vulnerability escalate the vulnerability to the person-in-charge of the project.

- If it's not a serious vulnerability then open an issue in GitHub and follow through on fixes.

- Maintain constant contact with the bug reporter and keep them apprised on the status of their report.

- Decide on payout amounts.

Rules and Scope can be found on https://bounty.decred.org/#Scope . This will be edited throughout the program as required.


# Who:

Current Validator List: dnldd, Degeri (me), matheusd, jholdstock, fernandoabolafio.

Website Development: fernandoabolafio, Degeri (me), jholdstock


# Costing and Funds:

Each contributor working on the program will be adding any time spent as a line item to their invoices via CMS.

The payouts for the vulnerability submitter has also been moved to the CMS system.

The time spent to validate and write up issues will be taken from the core development budget.

Each validator will not be spending more than 30 hours a month on validation.  (Currently, this averages to about 6 hours a month in total for all validators)



### Budget:

A maximum operating budget of **6500** USD for one year.

    Maintaining the bounty website and any updates. (2,000 USD)

    Defining policies/rules and scope (2,000 USD)

    Any other nonbounty expenditure like emailing, book-keeping, writeups, etc . (2500 USD) 

Note: I have intentionally overbudgeted to account for a 20% overspend.

Since we cannot predict the types of vulnerabilities and their severity it is not possible to have a fixed payout limit. So I am capping the maximum budget for payouts to be **100000 USD** for the duration of this program.



### Breakdown of spendings for the past 5 months:

#### Operating budget spendings:

Initial website development and launch: 1,300 USD

Bonus on website completion: 200 USD

Initial scope creation: 320 USD

Website/ Scope / Mail content edits: 380 USD

Bookkeeping and mail correspondence: 250 USD

Total: **2450 USD**


#### Bounty Payouts:


[Politeia cached user data needs to be cleared out on logout](https://github.com/decred/politeiagui/issues/1002): 72 USD

[Stakepool cached user data needs to be cleared out on logout](https://github.com/decred/dcrstakepool/issues/318): 72 USD

[Stakepool invalidate password reset token on email change](https://github.com/decred/dcrstakepool/issues/320): 150 USD

[Stakepool password reset token leaking to github](https://github.com/decred/dcrstakepool/issues/376): 135 USD

[Stakepool URL redirect](https://github.com/decred/dcrstakepool/issues/378) : 150 USD

Unpatched "Note" level vulnerability 1: 50 USD

Unpatched "Note" level vulnerability 2: 100 USD

Unreleased "Medium" level vulnerability 1: 3000 USD

Total: **3729 USD**


Investigating/Opening issues and discussion of vulnerabilities with devs (This pulls from the core development budget): 1130 USD

We have had a total of 58 submissions of which 9 of them were eligible for a payout. 8 of them have been claimed.


# Challenges and Self-analysis:

* We have a 15.5 % of reports being valid. 
* A large number of the rejected submissions are for out of scope or minor configuration related issues.
* Some of the submissions were not real vulnerabilities and showed that the bounty hunter has little knowledge of decred.
* We have only spent 3729 USD out of the 100000 USD for bounty payouts. 
* We should aim to attract more quality talent. 
* I have had multiple talks with people who run bounty programs for other cryptocurrencies. And this seems to be a common problem.
* We should not get a false sense of security assuming fewer payouts = more secure. 




# When and Duration:

This project will be approved for **1 year** or until the bounty/operating funds have been depleted.

** Note: ** I have increased the duration of the program from 6 months to 1 year. Initially, I thought that we could just approve a budget without a time frame but feel unsure about it. I am open to community feedback on this.