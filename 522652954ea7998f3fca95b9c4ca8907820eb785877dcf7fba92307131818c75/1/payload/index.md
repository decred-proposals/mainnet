Change language: PoS Mining to PoS Voting, Stakepool to Voting Service Provider
### What
Change the words we use to refer to:
*  Proof of Stake "mining" to "voting"
* "Stakepools" to "Voting Service Providers" (VSPs) 

This has been discussed several times, including in [this reddit thread](https://www.reddit.com/r/decred/comments/95r578/proposed_changes_to_decred_jargon/e3uu14p), and there always seems to be support for a change.

### Why
The use of "mining" in relation to Proof of Stake does not help to clarify what that is about, whereas "voting" captures it quite well.

"Stakepools" sound like mining pools but they are quite different - there is no pooling of work/rewards, tickets are called to vote independently. "Voting Service Provider" is a better fit because their role is to ensure that there's a wallet which can respond on behalf of the ticket online when it is called.

The more controversial point seems to be whether passing a Politeia proposal is necessary to change the language used in relation to the project. This seems like good practice to me, because it is important that terms are used consistently across platforms. 

### Who

The "Stakepools" term in particular would have to be changed on a number of pages of [dcrdocs](https://github.com/decred/dcrdocs), [dcrweb](https://github.com/decred/dcrweb/), [decrediton](https://github.com/decred/decrediton), [dcrdata](https://github.com/decred/decrediton) and on the sites of the [Stakepools](https://www.decred.org/stakepools/) themselves. Ideally at around the same time.

That's a fairly major community coordination issue, as it involves many different people who maintain those sites/software.

### How

I have prepared [a pull request](https://github.com/decred/dcrdocs/pull/590) which changes the terms on docs.decred.org, but merging that in isolation will just put docs.decred.org out of sync with all of the other sites where the terms are used.

This proposal is an opportunity for people who don't like the change or don't want to implement it on their site to speak up and vote No. If you support the change of terms you should vote Yes, of course. If you think this should not be put to a vote you could Abstain, or submit a counter-proposal to adopt a policy like "Politeia proposals should not be used to change the language people use"

### When

If this proposal passes, I suggest merging the pull request that changes [docs.decred.org](http://docs.decred.org) one week later, so that others have time to prepare updates to their sites (not mandatory).