Planet Decred launch proposal

**Planet Decred (PD)** is an initiative from **Raedah Group (RG)** to create broader access to the open source projects we are building for decred, while further decentralizing the development infrastructure for decred.
The primary mission of PD is to actively work towards realizing the decentralized promise of decred.

**Motivation**

As RG development has expanded for decred over the years, and the decred developer community has grown as a whole, it has become clear we need to improve our structure to be able to scale the work we are doing. When the team was small we were able to communicate via ad hoc methods. We have outgrown those tools. Many times we have had new developers who want to work across several decred projects, or existing developers who are already working on other decred projects, who want to contribute to the projects that RG is the primary maintainer of. We have done what was necessary to be operating as an open source project, but the repositories have remained listed under raedahgroup. Decred needs to have a decentralized development infrastructure. This will create resiliency in the servers that are required for development teams to operate. Our aim is to do this in a way that maintains compatibility with existing decred infrastructure.

**Actions**

**Matrix Chat** - We have already setup a planetdecred.org matrix chat server, and all developers from RG have moved project discussion to it. This allows us to utilize matrix's decentralized federated mode to facilitate communication between multiple teams, such as with the decred.org matrix server. We also already have a bot setup that is sending github notifications to our rooms. Instructions for connecting with us are listed on [planetdecred.org/chat](https://planetdecred.org/chat) . Decred community members already on matrix can join #planetdecred:planetdecred.org on matrix to join PD discussion. ~50 hours of work was put in to creating and administering this so far.

**Dcrdata** - RG is a co-founder and a major contributor of code and features for dcrdata. For PD, we have already setup and will continue to operate additional dcrdata servers for mainnet https://explorer.planetdecred.org/ and testnet https://testnet.planetdecred.org/ . We also run a dcrdata dev server for our team members to quickly get access to a dcrdata development environment with the needed historic data and disk space. We intend to add additional style customization capability to dcrdata so server admins can easily customize the look of individual instances. All code contributions will continue to be submitted to the current dcrdata repository residing at github.com/decred/dcrdata so that all admins of dcrdata can benefit from these improvements. The new PD dcrdata servers had ~25 hours of labor put into setting them up.

**Other Servers** - There are other servers we can setup to make the decred server infrastructure more decentralized and resilient. Decred mainnet and testnet network seeders, a testnet faucet, a fallback privacy mix server, and running a planetdecred vsp.  We can also improve our secure build process in order to add signed builds for dcrd, dcrwallet to the PD download section, as well as direct downloads for android mobile wallet apks. 

**Code Management** - RG has been the maintainer of the mobile applications and associated repositories. With the approval of this proposal, RG will transfer the repositories we maintain (dcrandroid, dcrios, dcrlibwallet) to the project account 'planetdecred' on github. All other future work related to PD and that becomes funded by the decred treasury will also reside at this location. Github is being used so that we maintain crossover compatibility with the existing 'decred' project account on github. We would consider other options besides github in the future as needed.

**Website & Blog** - We have setup and will continue to maintain a website at [planetdecred.org](https://planetdecred.org) with information about our projects and a blog at [blog.planetdecred.org](https://blog.planetdecred.org) for announcements and communication. PD contributors will be asked to maintain individual twitter accounts that they post updates to, and these will be syndicated via [twitter.com/planetdecred](https://twitter.com/planetdecred) . ~25 hours was put into creating the website and blog.

**Decred Power** - RG recently released a decred directory project, [decredpower.com](https://decredpower.com), that has received praise from the community. The Decred Power directory would become a PD project. We will continue to keep the directory up to date, as well as improve functionality to keep it easy to use as it grows, and add other style options to appeal to broader audiences. ~40 hours have been put into this website.

**Local Events** - RG developers have been organizers and promoters of decred in their regions. We have been able to do these small events at a low cost by gathering many decred volunteers and enthusiasts to support the effort. We would continue to support these efforts as opportunities arise and will put an allocation in our budget for this.
Examples of successful events that RG managed have been in Africa, South East Asia, and in the NW USA are:

- [2018 portland street fair](https://twitter.com/raedahgroup/status/1039315242684166144)
- [2019-05 blockchain ai digital assets conference lagos nigeria](https://github.com/decredcommunity/events/blob/master/reports/20190524-blockchain-ai-digital-assets-conference-lagos-nigeria.md)
- [2019-07 cointime summit ho chi minh city vietnam](https://github.com/decredcommunity/events/blob/master/reports/20190725-cointime-summit-ho-chi-minh-city-vietnam.md)
- [2019-09 bali block confex legian indonesia](https://github.com/decredcommunity/events/blob/master/reports/20190928-bali-block-confex-legian-indonesia.md)
- [2019-10 blockchain digital asset conference abuja nigeria](https://github.com/decredcommunity/events/blob/master/reports/20191004-blockchain-digital-asset-conference-abuja-nigeria.md)
- [2020-02 decred crypto hangout lagos nigeria](https://github.com/decredcommunity/events/blob/master/reports/20200208-decred-crypto-hangout-lagos-nigeria.md)


**Who**

Contributing to PD projects will be open to all qualifying decred contractors. Much of this work is already being performed by RG as demonstrated by the work already completed. Website front end work was done by @rickmort, @m4nnrs, and @daniellamarr. Current active dcrdata contributions on our team are @ademuanthony, @ekeh, @mkingori. Local events have been attended by numerous developers. All server administrations tasks are currently performed by @raedah until there is someone else qualified to contribute. All work done by RG is overseen and directed by @raedah. RG will be the proposal holder and manage the proposal's budget.

**Cost**

No compensation is being requested for work that is already completed. The total cost of this proposal is $22,000. This budget would run for a period of 6 months, July 1st 2020 through Dec 31st 2020. The cost of this proposal is an upper limit. Only work completed will be billable. 

6 month budget breakdown is: 

- Server hosting: $3000
- Server administration: $6000
- Website maintenance planetdecred.org: $2000
- Website maintenance decredpower.com: $3000
- Dcrdata style capability: $5000
- Local events: $3000
- -**Total** $22,000
