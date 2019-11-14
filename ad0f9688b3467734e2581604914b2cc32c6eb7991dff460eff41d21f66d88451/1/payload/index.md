TinyDecred Budget

TinyDecred (TD) is a Python toolset and wallet for Decred that was 
[adopted by stakeholders](https://proposals.decred.org/proposals/20e967dad9e7398901decf3cfe0acf4e0853f6558a62607265c63fe791b8b124) 
in August. TinyDecred exposes the features of Decred to a massive community of 
Python developers and tinkerers. Since TD was adopted, I've added lots of script 
support as well as VSP ticket purchasing, and I remain dedicated to developing 
TD into a jewel of the Decred ecosystem.

**This proposal does not seek any up-front funding**. I'm pursuing stakeholder 
approval for a set of development objectives and a budget for 
accomplishing the work. All work will be billed against the treasury on an 
hourly basis by approved contractors at their standard rates.

While I don't want to limit organic development, stakeholders deserve to know 
what they're paying for. Any work that falls outside of the scope of 
the development objectives listed below will not be billable to the treasury. 


## Development Objectives

All task durations are estimates.

**Database improvements** - *30 hours*

The current database is a hand-spun sqlite-based key-value database. This is 
great for our needs for a number of reasons, but we could easily add the 
ability to use the same database as an object database, which is fitting for 
high-level wallet functionality.


**Complete staking** - *60 hours*

Script support, rudimentary UI, and VSP ticket purchases are done and will be merged soon. 
Still needed are revocations, governance controls, and various data views.
dcrstakepool just added accountless ticket service too, so that should be 
implemented, possibly as the default.


**Full account support** - *30 hours*

The low-level code fully supports accounts, but only a single account is enabled
in the wallet until a reasonable UI is developed. This work will enable multiple accounts, 
adding an account selection screen, configuration screen, and historical data views.


**Medium tutorial: On-chain trivia game** - *40 hours*

I'll write a programming tutorial to create an on-chain trivia game.

Technical details: the hash of some funder-defined answer string is the only input required 
to satisfy a redeem script for a pay-to-script-hash output. The funder creates a question-answer pair, 
sends some funds to its address, then advertises their game. Anyone can then guess the 
answer. Once a player guesses correctly, the transaction will be broadcast to claim the funds
for the winner. I'll walk readers through writing a Python script for the funder 
and one for the player.


**Full node interoperability** - *120 hours*

TinyDecred could start and stop dcrd on its own, and use dcrd's API instead of a 
block explorer. TD is designed to stay running all the time without cluttering 
your desktop, which makes it a great control interface for dcrd. Subtasks here include
writing a node wrapper, an RPC client, and a new `Blockchain` class that will work 
with the full node. 


**Python SPV node** - *140 hours*

For a typical wallet user, running in SPV mode is preferable from a security and system
requirements perspective. This is a middle ground between full-node interoperability, 
which is highly secure but requires additional software and quite a bit of disk space,
and an explorer-based light wallet, which makes installation and configuration easy, 
but at the cost of security. 
With a Python SPV node, there would be no additional installation requirements, 
and the level of security is infinitely better since applications can verify transactions 
directly against the blockchain. The minimal disk requirements of an SPV node would allow someone to 
fire up TD on virtually any device with Python support.


**Multi-asset** - *80 hours for BTC, 5-10 hours each for a handful of clones.*

TinyDecred has all the crypto stuff already. We just need some additonal script support, 
a BTC version of the wallet, and a sensible UI. The BTC wallet will mostly
be a pared down version of the Decred wallet, which is already in good shape, 
but handling SegWit will take some work.


**Lightning wallet** - *200 hours*

This should be interesting. I have a lot more research to do here, but the user 
should have the option of selecting a TD UI focused on a daily-use lightning 
wallet, with a standard wallet as a "bank" they can use to fund it. Not two 
separate wallets, but a hybrid wallet.


**Decred DEX** - *160 hours*

Exchange between two supported assets. This must come after multi-asset for
obvious reasons. Luckily, I know a guy who works on the DEX, so this should be a 
breeze.


**Decred Privacy** - *200 hours*

Decred's privacy solution is now available. From a UI perspective, making 
transactions private should be as simple as flipping a toggle switch on the 
TD interface. Concrete implemenatations already exist in Go, so this is mostly 
just code translation and UI work.


**General Maintenance** - *60 hours*

The README should be expanded and user documentation written. 
Existing code should continue to be tested, analyzed, and refactored.
Eventually, TD should get on a release schedule and packages prepared
for the Python Package Index for near-instant installation with a single command.


## Budget Request

I'm requesting a **billing limit of $30,000**. Note that the limit requested is 
not enough to complete all of the tasks listed. When the budget becomes 
exhausted, I will return here with a performance report and an updated objective
list to request reapproval.