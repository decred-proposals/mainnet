GoDCR: GoLang Native Desktop Wallet

## GoDCR: GoLang Native Desktop Wallet

GoDCR is a desktop wallet for Decred. It was written using Gio (gioui.org), a GoLang library for implementing immediate mode user interfaces. GoDCR shares backend golang code with the decred mobile wallets via the dcrlibwallet component. A short video demoing it was shown recently here https://twitter.com/planetdecred/status/1290753362829352960

### Overview
GoDCR is an initiative created by Raedah Group. This came about through earlier experimentation with several user interfaces that occurred in 2018-2019 that can be seen here https://github.com/raedahgroup/godcr-old/wiki/Screenshots. In the process of evaluating UI toolkits, we found gio. It met the tight integration, quality standards, and visual customization requirements we had, and so it was decided that we would focus all efforts on bringing godcr with gio to a demoable app. The code is available here https://github.com/planetdecred/godcr . This work occured throughout 2020 till now. The godcr team consists of oshorefueled, sirmorrison, song50119, and codemaestro64.

Our goal since releasing the demo video has been to get decred vspd v3 support added, which has made good progress here https://github.com/planetdecred/dcrlibwallet/pull/163 . A major benefit of building capabilities for godcr is that the mobile wallets will also get access to all new features made available in dcrlibwallet, just as godcr benefited from all the capabilities already written for the mobile wallets. When staking capability is complete, we plan to do an official releases of godcr for window, mac, and unix platforms. Current measurements show we will be able to release a binary that is light on dependencies, compact in size, and fast.

In advancing the state of this software, we are collaborating with the gio project by making upstream contributions for new gio components we build and discussing with the gio team about upcoming features. As gio is a crucial component for godcr, this proposal will include sponsorship of $1000 per month for the gio project. This has been discussed with Gio lead Elias Naur, and Decred will be listed as a sponsor on the gio website. The full success of godcr is being rooted for, and godcr aims to be a hero application to demonstrate what gio makes possible with golang.

Upcoming features:
- Staking, https://github.com/planetdecred/dcrlibwallet/pull/163
- Politeia integration, https://github.com/planetdecred/godcr/pull/254
- Improved design implementation based on new mock-ups, https://github.com/planetdecred/godcr/issues/259
- Coin control custom input selection, https://i.imgur.com/Ewo7B0w.png
- Dark mode

### Details
Work will be direct by Raedah of Raedah Group. We will be continuing with the same team listed above that brought godcr to where it is today. That is, oshorefueled, sirmorrison, song50119, codemaestro64. Design mockups will come from Morphymore. Work will be done by developers based on availability. Work from Sept 2020 and Oct 2020 will be billable under this proposal, and 6 months forward from Nov 2020 through April 2020. An allocation of $7500 per month, covering 8 months for this proposal, with a proposal billing limit of $60,000 USD. This budget has been created based on average ongoing costs with additional allowances allocated to allow for other developers to join our efforts. All research and development work done prior to September, no compensation is being requested for.
