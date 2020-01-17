Decred Open Source Research Program: Phase 3

This proposal requests renewed funding for the Decred Open Source Research program, on the same basis as [phase 2](https://proposals.decred.org/proposals/67de0e901143400ae2f247391c4d5028719ffea8308fbc5854745ad859fb993f) (contributors bill at their hourly rate), but with an increased budget (by $5k) of $25k. The idea behind the increase in requested budget is that I'm optimistic collaboration with other contributors will increase. 

The proposal is composed of two parts: a report on phase 2, and a plan for the next phase.

Edit 1: Added summary overview of deliverables. In response to comments indicating a preference for Decred-related research, I am **capping the budget which would be spent on more general research (cryptocommons.cc, crypto-governance-research) at $10,000**, ensuring that at least 60% of the requested budget would be spent on research which is directly relevant to Decred (Pi Research, Politeia Decision Support, on chain analysis).

# Report

The [blockcommons.red](https://www.blockcommons.red/) website was created as part of the research program to showcase its outputs (plus some other stuff). It is an [open source](https://github.com/block-commons/block-commons) static site built with Hugo. It presents blog posts and research reports, and also serves as a home for the [crypto-governance-research](https://blockcommons.red/crypto-governance-research/overviews/) project and Politeia Digest.

The [cryptocommons.cc](https://www.cryptocommons.cc/) book-site was the largest output from phase 2 of the research program. Over the course of phase 2 it went from a collection of notes to a ~45,000 word document that lays out a rationale for appraising blockchains as "commons based" infrastructure, and walks through applied examples of this kind of appraisal (based on the crypto-governance-research overviews).

Thanks to @jholdstock for introducing me to Hugo and help with getting these sites set up in a way that's good for users' privacy. Thanks also to @sænder for the epic [Block Commons graphic](https://www.cryptocommons.cc/the-block-commons.jpg) (which I have made heavy use of) and for some tips for how to make the sites look a little more aesthetically pleasing.

The other major new project in phase 2 involved collection and analysis of DCR market data. This started out as a way to [profile DCR's liquidity](https://blockcommons.red/publication/orderbook-analysis/), to provide information which would help the stakeholders make a more informed judgement about the market maker proposals. Since then, the sub-project expanded to monitor the markets and provide a [perspective](https://blockcommons.red/publication/mm-tracking-1/) (using public data) on whether the market making service is being delivered as promised by the approved market makers (i2 Trading).

I'm labelling this kind of ad hoc research into subjects that the stakeholders need to be "briefed" on as [**Politeia Decision Support**](https://www.blockcommons.red/project/politeia-decision-support/). If you have ideas for small projects like these relating to pressing issues let me know (particularly if you would also like to work on them).

The [Pi research project](https://blockcommons.red/project/pi-research/) continued to leverage the scripts developed during phase 1 and augmented these in a number of areas. Reports produced in this phase concerned [analysis of user activity](https://www.blockcommons.red/publication/users-review-201907/), a look at [ticket voting patterns](https://www.blockcommons.red/publication/mm-voting/) for the market maker proposals, and a [compendium](https://www.blockcommons.red/publication/politeia-at-1/) of stats and graphs to mark the first anniversary of Pi's launch. Regular use of the data processing scripts has continued to detect occasional bugs, which I report to the Pi devs.

In the [crypto-governance-research](https://github.com/RichardRed0x/crypto-governance-research) project, new pages were added for [EOS](https://www.blockcommons.red/crypto-governance-research/overviews/eos/) and [Algorand](https://www.blockcommons.red/crypto-governance-research/overviews/algorand/), old pages were polished as they were added to blockcommons.red, and an [overview of the concept of "staking"](https://www.blockcommons.red/publication/staking/) and the way it features in different projects was written.

## Deliverables

Summary list ordered by the time billed for each component.

* [cryptocommons.cc](https://www.cryptocommons.cc/) - a new static website which presents a new creative commons licensed book/thesis produced by the research program: Peer Production on the Crypto Commons. The site also offers ebook and pdf versions of the book, and a versioning system has been set up in the GitHub repository. 
* [Politeia Decision Support](https://www.blockcommons.red/project/politeia-decision-support/) - [order book investigation](https://blockcommons.red/publication/orderbook-analysis/), [MM report 1](https://blockcommons.red/publication/mm-tracking-1/), [MM report 2](https://github.com/RichardRed0x/exchange-data/blob/tradehistory/mm-tracking2/market-making-update2.md), unpublished follow up analyses and data collection to assist with c0 audit.
* [blockcommons.red](https://www.blockcommons.red/), new static website - setting up the site and transferring content (with some polish) from the various GitHub repositories where it is produced. Also includes some new content like a post introducing cryptocommons.cc and a retrospective on Politeia's first year.
* Pi Research - [user activity analysis](https://www.blockcommons.red/publication/users-review-201907/), [ticket voting patterns on MM proposals](https://www.blockcommons.red/publication/mm-voting/), [year 1 stats and graphs](https://www.blockcommons.red/publication/politeia-at-1/).
* [Crypto-governance-research](https://github.com/RichardRed0x/crypto-governance-research) - new pages for [EOS](https://www.blockcommons.red/crypto-governance-research/overviews/eos/) and [Algorand](https://www.blockcommons.red/crypto-governance-research/overviews/algorand/), [staking overview](https://blockcommons.red/publication/staking/).

# Plan

The plan is for the program to continue as it has been going. I thought about including the who/how/why sections but the answers have not changed since [last time](https://proposals.decred.org/proposals/67de0e901143400ae2f247391c4d5028719ffea8308fbc5854745ad859fb993f).

Here are some thoughts on the likely areas of work for phase 3, feedback is welcome.

The cryptocommons.cc site launched on Nov 1 as version 0.8, I have been taking a break from it since then but I plan to go back and add some more content and some polish, working towards a v1.0 release. I have started writing about large scale cryptocurrency adoption and the different visions of what this means. I plan to write about where we are now, what the next steps might be, and what the broader social impact would be for these different different versions or aspects of cryptocurrency adoption.

I plan to publish this new material as standalone article(s), then incorporate it within cryptocommons.cc. With the recent launch of the [nakamoto journal](https://nakamoto.com/), I'm thinking about submitting something related to this subject there.

Pi Research will continue in the background. When Politeia switches from git to tlog data storage this will probably require some work to update my data processing scripts. I might also take that opportunity to automate the [@pi_crumbs](https://twitter.com/pi_crumbs) twitter account, one of the items mentioned in the last proposal which I have not yet taken on. 

I have recently started looking at Decred **on chain data** in more depth, after installing a local dcrdata instance and witnessing the treasure trove of information it makes readily available in its database. 

I am still at the exploratory stage but I have some ideas about directions to take this in (these are probably largely inspired by previous discussions in the community, and @bee has some [issues](https://github.com/RichardRed0x/decred-research/issues/2) I can mine for more ideas).

* Testing or auditing stakeholders' privacy, particularly when participating in governance. The privacy implications of transacting on UTXO-based blockchains are quite well understood now, but ticket buying and voting on consensus and Politeia proposals are all actions which are unique to Decred. I plan to look at ticket buying and voting to see if these actions offer ways to diminish participants' privacy. This is a delicate subject, and if I were to discover anything significant that can be addressed, I would wait until steps had been taken to address the issue before publishing about it.
* Building on this, I'm interested in profiling the stakeholders' Pi voting decisions to see if there are any interesting clusters that tend to vote the same way on proposals of the same type.
* Looking at the flow of block rewards to see what different constituencies are doing with their DCR, the obvious question being whether PoW miners are selling or staking. This has been on my radar for a long time, after recent explorations it seems achievable.
* Collaborating with and/or replicating the work of other researchers who are looking at Decred's on chain data. With @checkmate and @permabullnino now working on this kind of data I'm more interested to engage with it because there could be opportunities to help each other out and improve our outputs, plus sometimes it's more fun to work with other people.

Collection and analysis of Decred-related (social) media data is still on the table (since the original [proposal](https://proposals.decred.org/proposals/5d9cfb07aefb338ba1b74f97de16ee651beabc851c7f2b5f790bd88aea23b3cb/comments/13)). I'm more interested in this now than I have been for a long time, but it's still quite a low priority.

I am also considering making another static Hugo site to showcase all of the outputs from all of the Decred research projects that are now active. I feel that we should have this kind of resource for collecting and showcasing  outputs from research projects funded by the Treasury. I think it probably warrants a larger collaborative effort and maybe its own proposal, but failing that I would probably make something simple myself within the next 6 months.

In general, I work on whatever seems to be the most pressing or useful task at the time. So if some fresh need emerges in the realm of Politeia Decision Support, either through a new proposal or discussion, that would tend to take priority.

### When

The research program would continue until the requested budget ($25,000) runs out, which would probably be around 6 months. A report on the program's activities would be prepared at that time.