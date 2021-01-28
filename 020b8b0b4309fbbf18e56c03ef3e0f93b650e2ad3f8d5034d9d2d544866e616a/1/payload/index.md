Open Source Research 2021

# Open Source Research 2021

## Summary 

This proposal requests a budget of **$40,000** for 2021 funding for the Open Source Research Program. $9,150 of this is earmarked for a Decred data tracking initiative led by bee, which is described at the end of the proposal.

Otherwise scope of the research program will work as before, it is outlined below but can be extended by me (Richard) as circumstances develop, but with a condition that a maximum of $10,000 will be spent researching subjects that are not directly relevant to Decred.

## Phase 3 Highlights

* [Decred blockchain analysis - Part 1](https://blog.decred.org/2020/06/08/Decred-blockchain-analysis-Part-1/) 
* [Decred Blockchain Analysis - Part 2 PoW wow](https://blockcommons.red/post/dcr-on-chain-2/)
* [Crypto Commons 2020 review and v1.0 changelog](https://blockcommons.red/post/ppcc-changelog-2020/) to accompany a [major upgrade to version 1.0](https://github.com/block-commons/cryptocommons/pull/27) of cryptocommons.cc
* New crypto governance research pages ([Algorand](https://blockcommons.red/crypto-governance-research/overviews/algorand/), [Polkadot](https://blockcommons.red/crypto-governance-research/overviews/polkadot/), [Uniswap/SushiSwap](https://blockcommons.red/crypto-governance-research/overviews/uniswap/)) 
* [Social Media Stats](https://github.com/decredcommunity/social-media-stats), led by @bee
* [Market Maker data collection phase 1 wrap-up](https://blockcommons.red/publication/mm-phase1-wrapup/)
* [Year two of Decred's Politeia in numbers and graphs](https://blockcommons.red/publication/politeia-at-2/)

The budget for phase 3 was $25,000, which lasted until December 2020. The amount which went to research subjects not directly relevant to Decred (cryptocommons.cc and crypto governance research) was around $7,000.

### Chain Analysis

In 2020 it was mostly me (Richard) working on [phase 3 of the Open Source Research program](https://proposals.decred.org/proposals/e367564), and most of the time I have spent working on it has been on the blockchain analysis track, developing the core functions that all of the analysis is built on - and also improving my level of understanding of the chain data and what it means, how it can be utilised. You could see this as establishing a foundation that will allow me to construct more and better reports in the future, much faster now that the basic tools are solid. The progress on the clustering, cluster analytics and "flow tracking" tools has been hard won, through painful hours spent looking for issues with the data-sets being produced, then trying to pin down the reasons why any observed errors crept in.


The scale of the database presented some challenges for working with it effectively - I run a lot of queries while exploring the data, and when I have code to deploy on the whole chain it can mean leaving a computer to churn through it for days. This adds to the difficulty of everything about this research, because it's difficult to get into a flow with the constant pausing to wait for queries to execute, and the pseudonymous nature of the addresses and hashes means it is difficult to find one's orientation every time one sits down to look at a table of this kind of data and check it or interpret what it means.

I had a choice here to handle the scale, between building out my own setup or using something like Google's BigQuery - a cloud service which presents an SQL-type interface to access data and charges per query, but can execute those queries rapidly on very large datasets. I have used BigQuery before and it may have been the most efficient way to tackle this, it would certainly have been easier, but I thought that because this is for Decred I should avoid the use of a Google service like BigQuery. The addresses table, which is the one I use the most for this, has around 46 million rows, which is about ten times more than I have ever worked with locally before on this kind of regular ongoing basis.

The upshot is that I built a nice data server with 64gb of RAM and an SSD drive (funded by myself) and got it set up on my network as a chain data crunching machine. I also learned a lot more about PostgreSQL this way, and I learned how to use some new packages for R, like ddplyr, which allowed me to construct complex queries much more quickly than I had been doing manually before, and to manage access to the database more efficiently.

In terms of the tools to work with this data, I have developed functions and scripts to:

* associate addresses likely belonging to the same wallet (clustering)
* track a set of credits to follow how it flows in the ledger, this has been applied to tracking PoW rewards, Treasury payouts, Airdrops and Founders' rewards.
* profile a set of addresses, tracking balance, type of transactions, where the DCR came from and went to - by using the flow tracking data referenced above
* aggregate the tickets for a cluster and how they voted on agenda and Politeia proposals
* turn these raw data-sets into network graph objects which can be visualized and against which network statistics can be calculated
* generate a number of other plots and statistics related to clusters or addresses

Probing Decred's mixing privacy is one of the aims of my on chain research, but it is only towards the end of the year that I reached a level of familiarity with the data that I could start to do this. So far I have some ideas and prototype code for how to profile the DCR going to and from mixing transactions, but nothing worth publishing yet.

Something I am conscious of here with the on chain clustering work in particular is stakeholder privacy. I'm not sure how I would feel if I was the owner of some of the addresses whose balances and transactions and votes are being publicly reviewed. It's a transparent public ledger, but not everyone is aware of how easily it can be read or what people can learn from linking small pieces of information. I take the step of truncating the addresses to just a few characters, but it wouldn't be hard for anyone with access to a dcrdata database and rudimentary SQL skills to undo that and get the full addresses. Maybe full addresses are fair game, it is a public ledger after all, let me know what you think in the comments. 

In relation to making the research open and reproducible, this poses some difficulties, because in practice none of the clustering analyses are reproducible without either building the clustered address lists first (I do this in a new table in the database) or importing it. I don't think it's necessarily in the stakeholders' interests to have me releasing lists of clustered addresses, and without those the code is no use, so in practice anyone wishing to use my code to reproduce analyses related to clustering would have a long road ahead of them which likely involved several weeks of database crunching.

In terms of the point of doing and publishing this research - whatever I have achieved as an on chain analysis novice with a budget of ~$15,000 is easily replicable by any well resourced entities with an interest in the blockchain or the people using it. Raising awareness of how this data can be (is being?) read has become a secondary mission for me to go with the on chain research, and for me at least improving my blockchain privacy means understanding more about how that data can be used.

I'm happy to see Stakeshuffle Stakey shuffling its way to Decrediton in v1.6, and have waited for this release before publishing much in the way of the clustering work. Doing this research makes me more keen to mix before spending, and I'm guessing that reading it will have the same impact on a lot of people, so I'm glad they will have the option to easily reach for Decrediton if they feel inclined to enhance their privacy.

This is an area where I would particularly like to hear from anyone who has a strong view - so far nobody has complained, so I'm hoping that means people are cool with it, and not just getting quietly upset about it and planning to vote no on my proposals! :)

I have a variety of different strands going with the on chain research now, and while most of them are not close to being finished I think there are a few that are going well. I was interested to see that the Coinmetrics team, who I respect as leading chain data analysts, released a [new analysis](https://coinmetrics.io/following-flows-a-look-at-miners-on-chain-payments/) in November looking at miner payments one hop out from the coinbase transaction. 

> Using a new methodology that looks at addresses one hop out from the  coinbase transaction, this report quantifies miner holdings and  activity. This approach improves on previous attempts at tracking miner  spending, which inadvertently measured pool operator activity rather  than miner behavior.

This seems like the kind of leap forward which one might have made after reading my first on chain report, released in June, which considered miner flows of DCR up to 3 hops from the coinbase and beyond. In any case, I took this as a good sign, that I have found my way to the cutting edge for some aspects of on chain research.

### Fun Stuff

In addition to learning some more advanced data-handling skills, I have been learning a few other things for fun. When I helped out with organizing Decred's presence at Consensus in May and recording the segments with other contributors before that, I picked up some basic video recording and editing skills, and  got interested to learn more.

I have been posting some of the products of my learning through play online, and they're mostly related to Decred in some way.

Clay Stakey was born, had his first [quick voting adventure](https://www.youtube.com/watch?v=6zAe6b50zwc), and also a [more dramatic and haunting episode](https://www.youtube.com/watch?v=hrqaF8sFquI) with a less happy outcome. I have also produced a music video for the DEX rap, but I have held off on releasing it because it features other characters too (Bitcoin Billy and Litecoin Larry), one of which is not yet available to trade on the Decred DEX server.

I also got a drawing tablet and produced my first computer-drawn animation, "[Ticket price all time highs again](https://twitter.com/RichardRed0x/status/1310700935216271360)", which became even more relevant recently as ticket price has surged past certain key levels.

I have not billed the treasury for anything related to this fun stuff, but it is in a way a by-product of the Research program, as that is what has led to me spending most of my time thinking about Decred and cryptocurrency. A lot of the clay animation idea development specifically happened when I was sitting daydreaming staring at an R terminal waiting for a query to return, expecting it to take a few seconds and then slowly realizing that there was some overlooked aspect (usually a missing index) which meant it was going to take hours to finish. The window where I was satisfied that my query was underway, but before I realized I was going to have to kill it and dive back into the code, was often quite fruitful creatively. This is the kind of tasty bonus you can get when you approve Open Source Research proposals!

I think I can probably make use of the drawing/animation skills to make educational/explainer videos, but I don't have inspiration for anything specific yet.

# Plan for Phase 4

## On Chain

I have a number of irons in the fire with the chain analysis, where the hard work of writing code to generate the data-sets, and checking that it's reliable, is mostly done. 

* Cluster-based history of the Decred chain - I am planning a big report just dedicated to looking at the history of DCR through clusters, or maybe a series of smaller reports looking at specific sub-groups (like the top miners example)
* Exchange analysis - Exchanges are key actors in any cryptocurrency, but they don't have any distinguishing features on chain. How much can we know about exchanges on the Decred chain?
* Governance analysis by cluster - The clusters offer a new way to link tickets and consider questions like how many different people/wallets are likely involved in voting, what the breakdown on a per wallet basis is, and which are the voting and not voting stakeholders, and whether there are wallets or entities which vote in interesting ways (e.g. contrarians).
* Mixing set analysis - looking at the flow of funds into mixing transactions, and from mixing transactions. There are some interesting analytics which could be developed here, and it would lead into the more probing analysis of Decred's privacy solution which I have been building up to.

I have also been thinking about ways to expand on what I'm doing with the on chain research. 

One idea is to consider other blockchains too, like Bitcoin, where I could make comparisons on high level trends, and look at the DEX transactions specifically. There is a lot more I can do with the Decred data first though, so that's possibly something to come back to in a subsequent proposal/phase.

## Cryptocommons.cc

Although cryptocommons.cc is up to version 1.0 now, there remain many open questions where it's not clear to me how things will go. I think it worked pretty well to release a blog post review of the content and year alongside the updated version of the book, but a year is probably too long a time period, and 18,000 words too many for one post. I will look to break this up in 2021 and do 2-4 updates spaced throughout the year. 

## bee's open data collection

*This section is written by @bee.*

My main work in Decred has been to produce [Decred Journal](https://xaur.github.io/decred-news/) with @richardred, @degeri and other contributors. Over time I noticed  that some content can be reused in interesting ways if organized  properly. After ~2 years certain ideas have matured to the point I would like to present and request funding to take them further.

Decred DAO generates a ton of data that could be collected, organized and aggregated to increase awareness and facilitate making better  decisions. My key requirements of data is it must be easy to access in  its entirety and it must be hard to lose. Git is pretty good at solving  that for small to medium-sized data sets. Once published, any researcher can download a full dataset in seconds for local studies, and any archivist can save everything to restore after a possible disruption (like censorship). All with strong integrity protections.

For each mini-project below I provide a quick intro, what works,  efforts spent so far, next tasks and budget for them. Reporting-focused  projects come with "editing and polishing services" included, which  should save contractors some of the less fun reporting work.

**[social media stats](https://github.com/decredcommunity/social-media-stats)**

Track social media metrics, assess growth and correlate it with various factors, compare accounts.

I've been posting stats of main SM accounts in Decred Journal but at  some point realized they could be reused by other researchers if  organized in a more "programmable" shape. In early 2020 I published data collected since 2018 in a simple but powerful [data format](https://github.com/decredcommunity/social-media-stats#data-format) together with a [tool](https://github.com/decredcommunity/social-media-stats/blob/master/tsu) to validate and view it. Over time the data evolved to track 80+  accounts, the tool evolved to help me snapshot them in ~30 minutes each  month, and @richardred wrote code to generate [charts](https://github.com/decredcommunity/social-media-stats/blob/graphs/graphs/index.md). So far I've put ~57 hours to bring it up and billed ~10% of it against the third research [proposal](https://proposals.decred.org/proposals/e367564).

Next I plan to automate data collection, add detection of interesting changes and close other tasks in my backlog. To support this I am  requesting $1,850.

It must be noted that this project overlaps in functionality with [dcrextdata](https://github.com/planetdecred/dcrextdata) but they work differently. dcrextdata is automated and has nice [live charts](https://dcrextdata.planetdecred.org/community), while this project allows to dowload all data for offline research  ("open data"), tracks much more accounts and has more data into the  past. In the future it might be possible to merge them and gain the  benefits of both.

**[network stats](https://github.com/decredcommunity/network-stats)**

Collect and analyze various stats of Decred network.

This project also originated from Decred Journal when in June 2020 @degeri wrote initial code to grab node version data from [dcr.farm](https://charts.dcr.farm/d/000000014/nodes). Since then I polished it and added missing features. So far I've put ~15 hours in it of which ~20% was billed.

Next I plan to organize and publish historical node data in a way  similar to social media stats, add pool hashrate data and start  collecting dcrstakepool/vspd stats to track vspd upgrade progress  (unless this is implemented elsewhere). For this I estimate $1,300.

**[events index](https://github.com/decredcommunity/events)**

Collect and organize event reports.

Events repo was started by @heyvj in April 2018 to collect best  practices and event reports. In June 2019 I took over, cleaned it up,  developed a standard format and began to collect reports more "aggresively", so to speak. Over 2 years [63 reports](https://github.com/decredcommunity/events/tree/master/reports) were collected but it was hard to "extract" them, I guess because they were time consuming to write and were hard to navigate.

To address these issues I developed a more lightweight [format](https://github.com/decredcommunity/events/blob/master/docs/index-spec.md) that is faster to write and importantly, contains *structured data*. This allows to generate interesting views/reports automatically ("show me events by date/country/people/etc"). I got [the site](https://decredcommunity.github.io/events/index/) up in November 2020 and it already has 42 events for Aug-Dec.

For events people it provides a single link that has everything about the event and can be used in reporting and billing. For auditors and  stakeholders it helps to verify the work. Finally, methods developed  here can be applied much more broadly to create structured open  source+data sets for all kinds of things (and I have 3-5 project ideas for Decred alone).

Since mid 2019 I've put more than 100 hours in it, of which ~25% was billed against US Marketing proposals as reporting and oversight.

Next I plan to keep collecting data and improving the site, using up to $1,500. Less data to process will cost less.

**[proposals repository](https://github.com/decredcommunity/proposals)**

Collect and organize proposal-related docs like progress and finance  updates, analysis, drafts, etc. Anything that doesn't fit Politeia.

Since early 2019 it has collected ~60 updates on approved proposals, [analysis](https://github.com/decredcommunity/proposals/tree/master/topics) of some proposals to support decision making, and its own data format  to enable interesting features in the future. I've put ~23 hours in it  so far, mostly to collect and polish the updates.

Next I want to create an index of proposals that stores important  information not formally recorded by Politeia like total USD budget,  start and end date, key people, domain and so on. Most of that data is  available in @richardred's [csv file](https://github.com/RichardRed0x/pi-research/blob/master/analysis/pi-at-2/Politeia-proposals-2years-coded.csv) that I'll try to reuse. Raw data will be useful for research and audit  on its own but we can get much more from it. Building on top of it I  will generate a static site similar to [events site](https://decredcommunity.github.io/events/index/) that will expose all this data to "normal" viewers and make the updates easier to locate. For this I request $2,700.

**[translations index](https://github.com/decredcommunity/translations/blob/master/index.md)**

Maintain a list of all translations to track contributions, avoid duplicate work, and plan what to translate next.

This repo was started in late 2018 by @kozel to coordinate people who translate Decred content. Throughout 2019-2020 @kozel and I have  indexed a number of translations and collected some effort stats. In Aug 2020 I "took over" the repo, converted the index to CSV and added all  translations I could find. Today it lists [300+ items](https://github.com/decredcommunity/translations/blob/master/index.md) and is updated monthly. Overall I've spent ~28 hours to collect and organize this data.

Next I plan to keep collecting data and convert it to the YAML  database similar to the one pioneered by the events index. It will allow to capture more useful data and generate index pages by language, by  translator, by source article, etc. For that I request $700.

**projects map**

Navigate Decred projects and find where to join.

Once in a while newcomers ask where to contribute and what  programming languages they need to know. A good existing resource is the [dev docs page](https://devdocs.decred.org/projects/), but it only lists ~17 main projects. Another is the [ecosystem map](https://www.reddit.com/r/decred/comments/k9g76v/decred_developer_ecosystem_repositories/) of 120+ repos but it only has links.

I'd like to create a better map by reusing ideas and code from the  events index and building a site where you can navigate by programming  languages used, see project status, descriptions and other useful data.  For this I would use up to $1,100.

Total limit for the above projects is **$9,150**.

I cannot say if I will finish everything but I will try to not leave  half-completed tasks. Any unused funds will stay in the treasury.

I plan developing these projects in any case but funding will be very helpful and signal demand.

**other**

I have more project ideas nearing the development phase. One is to finish my work to automate the [mapping](https://github.com/RichardRed0x/decred-media-tracker/pull/24) of Decred-related media articles (the code is ~50% complete). Another  is to map the Decred ecosystem by building an index of all exchanges,  payment processors, and Decred-related services with interesting  metadata like jurisdictions, key dates, significant events, community  test results, etc. And another is to apply similar principles to crypto  tipping to make it more decentralized and private. When I have something to show from these efforts I'll start billing or create another  proposal if necessary.

If you have any preference about priority of these projects or their features please let me know in the comments.

The total budget of this proposal is limited to **$40,000** to be used throughout 2021 or until the funds run out.