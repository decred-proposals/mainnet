Decred Open Source Research proposal: Phase 2


This proposal requests renewed funding for the Decred Open Source Reserach program, and also changes the way the program will run. The budget requested is $20,000, which is anticipated to last for around 6 months.

The proposal is composed of two parts: a report and retrospective on the program so far, and a plan for the next phase.

## Report

The research program got started with [this](https://proposals.decred.org/proposals/5d9cfb07aefb338ba1b74f97de16ee651beabc851c7f2b5f790bd88aea23b3cb) Politeia proposal which solicited ideas for research projects and asked Politeia participants to up/down vote on the comments to signal which topics/ideas were of interest to the community.

In some ways this worked well. The two highest scoring top level comments are for Politeia Research and Governance Models Research projects. I took these scores as a mandate to spend research program time on these projects. Together they account for the great majority of the time I have spent working on the research program. This suited me well, because they were the projects I found most interesting to work on. Without the comment votes as input I would probably have spent more time on projects like [Decred Media Performance](https://proposals.decred.org/proposals/5d9cfb07aefb338ba1b74f97de16ee651beabc851c7f2b5f790bd88aea23b3cb/comments/13) or [Cryptocurrency social media research](https://proposals.decred.org/proposals/5d9cfb07aefb338ba1b74f97de16ee651beabc851c7f2b5f790bd88aea23b3cb/comments/2), because they seemed to offer more tangible outputs for Decred. In short, the comment voting was good because it allowed me to focus on the projects I found interesting, without worrying about whether research on subjects like the governance of other projects would be considered out of scope by stakeholders.

This approach also had some drawbacks:

- After a week or so, the rate at which people were commenting and voting dropped off. Ideas submitted later had lower scores but probably because there was less attention on the proposal's comments generally.
- The proposal probably hung around on Politeia too long and got in the way, until it was abandoned.
- Comment voting is gameable while Politeia accounts are cheap, so it should not be relied on too heavily.

I was hoping that the open proposal on Politeia would encourage others to submit their own ideas or take on some of the good ones already proposed. I had thought that the research program might make a good starting point for a new contributor to Decred. There were some good ideas in the comments, but having the research program serve as a way in for new contributors didn't really work out. Only two people who were not already Decred contributors expressed interest in contributing, and in the end neither did. A big issue here was that in order to get paid for their work on the research program, participants would have to be cleared as a new contributor to submit invoices. I was not able to give assurances that solid work on the research program would definitely be paid for, as it involved this larger process of being cleared to submit an invoice.

Collaborating with other Decred contributors was more fruitful, @s_ben and @degeri helped out with aspects of the research that I did not have the time or skills for. This went more smoothly because there wasn't the friction of needing to make a broader call about whether someone should become a contractor before they could get paid for their work.

Below are some highlights from the research projects that were worked on.

[**Pi Research**](https://github.com/RichardRed0x/pi-research)

- R [code](https://github.com/RichardRed0x/pi-research/blob/master/data-collection/functions-pi-analysis.R) to parse the Pi data [repository](https://github.com/decred-proposals/mainnet) files and extract data-sets that represent proposals and their comments and votes.
- Writeups about analysis of Pi [comments](https://github.com/RichardRed0x/pi-research/blob/master/analysis/comments-and-updown-votes/comments-analysis-writeup-2018-11-19.md) and votes, a [look](https://github.com/RichardRed0x/pi-research/blob/master/analysis/voting/early-voting-influence.md) at voting over time patterns
- @s_ben wrote [piparser](https://github.com/s-ben/piparser) to extract timing information from the commit history of the Pi data repository
- Code to generate [graphs](https://github.com/RichardRed0x/pi-research/tree/master/analysis/voting/img/new-voting-over-time-graphs) showing voting over time for proposals, shared in chats, in pi digest, and on twitter. I believe the voting graphs and @s_ben's work on piparser served as inspiration or guidance for the proposal voting charts now available on dcrdata alpha.
- Code to automatically calculate stats and prepare blocks of [text](https://github.com/RichardRed0x/pi-research/blob/master/analysis/journal-pi.md) for inclusion in Pi digest and the Journal.
- [Exploration](https://github.com/RichardRed0x/pi-research/blob/master/analysis/voting/quorum-change-examples.md) of how the Politeia quorum requirement works and how alternative formulations would work differently (in terms of which proposals would fail to meet it)
- By processing and analyzing the formal record of proposal voting in the repository (and comparing this to the proposals site), I spotted signs of a couple of bugs with Pi and reported them to the developers.

[**Crypto governance research**](https://github.com/RichardRed0x/crypto-governance-research)

- This project is based on the [Governance Models Research](https://proposals.decred.org/proposals/5d9cfb07aefb338ba1b74f97de16ee651beabc851c7f2b5f790bd88aea23b3cb/comments/14) comment thread.
- It started as an effort to come up with a standard set of [questions](https://github.com/RichardRed0x/crypto-governance-research/blob/master/questions.md) about how blockchain projects are governed and compile [answers](https://github.com/RichardRed0x/crypto-governance-research/tree/master/answers) for interesting projects. This format is still evolving as additional people cover additional projects, and I am working on a complementary condensed version that relates to staking specifically.
- I have added [data-sets](https://github.com/RichardRed0x/crypto-governance-research/tree/master/governance-proposals) representing the proposal voting histories of Decred, Dash, Aragon and Cosmos. This was inspired by seeing some good articles about participation in blockchain governance which used weak data for Decred. The intention is to make this data more accessible and provide a useful resource to people who are studying blockchain proposal voting.
- I am working on a full length article which uses the concepts of common pool resources and commons-based peer production to develop a framework for understanding where the power lies in a cryptocurrency's ecosystem, how well the incentives of the various constituencies are aligned, and how effectively participants coordinate.

**GitHub analysis**

- [Contributor tracker](https://github.com/degeri/decred_contributor_track) that parses Decred repository commits, identifies new contributors and pulls out some stats. This automates the generation of some stats for the Journal.
- [GitHub Bigquery](https://github.com/RichardRed0x/github-bq) repository which obtained bulk GitHub data from the Github timeline and used it to look at forks of Decred repositories and historical activity levels of Decred repositories.

## Plan

The plan I am proposing for the next stage of the research program is about minimizing friction. It is based on my experience of being a Decred contractor so far, and aims to make working on this research program as low friction as the other aspects of the project I have worked on. There won't be a seperate proposal for collecting and voting on ideas, but feel free to comment with ideas on this proposal.

### Who

I would take the lead and work with other contributors as it makes sense. For the reasons outlined above, it seems unlikely that people who are new to the project would end up working on this, but I am open to that possibility.

### How

I will continue to work on the governance and Politeia research projects, but may also explore other subjects that seem relevant and interesting. Following up on subjects that are being discussed in the community has often been a fruitful approach, as it can involve asking questions I would not otherwise have asked, and going down some interesting rabbit-holes.

I also listen out for feedback about which aspects of the research people find useful and take this on board. For example, the decision to stop pushing forward with the git analysis work was made by consensus between @s_ben, @degeri and I, based on our perception of a general lack of interest. With more contributors to the research program, I expect decision making would move towards this kind of rough consensus approach.

### Why

My rough criteria for what fits into the research program is that it does at least one of these:

- provides stakeholders with useful information
- provides contributors/contractors with useful information - ranging from the answer to a specific important question, to neatly packaged information that eases workload elsewhere (e.g. Journal stats)
- provides information which helps to promote a better understanding of the cryptocurrency space

### What

Next steps for Pi Research are to integrate the new username lookup feature to generate accurate user stats, and possibly polish and schedule the data collection scripts in such a way that they could power a twitter bot. As more proposals pass through Politeia, it will also be interesting to go back and revisit the analysis of how it is working.

For the crypto governance research project I plan to finish the long-form article I have been working on. This is being written in the style of a Medium post initially, but I think it may also lend itself to a more formal academic style writeup. The way this is coming together is that the article puts forward my perspective on how to understand the "governance" of blockchain projects, and this leads on to the analysis of specific projects according to that framework. The project profiles in the repository will be the basis for those analyses.

### When

The research program would continue until the requested budget ($20,000) runs out, which would probably be around 6 months. A report on the program's activities would be prepared at that time.