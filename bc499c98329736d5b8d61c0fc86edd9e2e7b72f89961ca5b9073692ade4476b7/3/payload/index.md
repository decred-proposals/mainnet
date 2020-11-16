Mobile Wallets 2020-2021

## Mobile Wallets 2020-2021

This proposal is for continuing work on the Decred Mobile Wallets for Android and iOS platforms. This covers all work for the mobile applications under a proposal, which were previously being covered by the Decred treasury as part of core development.

- Play Store - https://play.google.com/store/apps/details?id=com.decred.dcrandroid.mainnet
- iOS link - https://apps.apple.com/us/app/decred-wallet/id1462247643

### Past

Raedah Group founded the mobile wallet effort at the beginning of 2018 by bringing on Collins for android development and Macsleven for iOS development. There have been many contributors over time, but these founding developers have remained consistent on the project. Both projects use shared golang code from dcrlibwallet which was built to work with gomobile. The mobile wallets have support for several language translations that came from community contributors.
An overview of all contributions can be seen at these links.

- https://github.com/planetdecred/dcrandroid/graphs/contributors
- https://github.com/planetdecred/dcrios/graphs/contributors
- https://github.com/planetdecred/dcrlibwallet/graphs/contributors

This is the timeline of major releases. Several other minor releases also occurred for bug fixes and keeping up with the current network consensus rules.

- February 2019, dcrandroid v1.0 released, https://www.reddit.com/r/decred/comments/am7j40/decred_wallet_for_android_v10_released/
- July 2019, dcrios v1.0 released, https://www.reddit.com/r/decred/comments/cbjqff/decred_wallet_for_ios_v100_on_the_app_store/

   After the initial releases were completed, support for multiple wallets was added and a full user interface refresh occurred.

- June 2020, dcrandroid and dcrios v1.5 released, https://www.reddit.com/r/decred/comments/hc5jut/decred_mobile_wallet_v150_has_been_released_for/

### Current & Upcoming

Development is ongoing. Essential feature milestones have been reached, but there remains additional features to be developed. We need to keep adding new capabilities from the decred ecosystem as they become available. The current team also has Dreacot contributing for android and Justindo contributing for iOS. They have been consistent contributors for several months. All developers have matrix accounts on the planetdecred.org server. The projects are maintained in an open source fashion at github.com/planetdecred . A matrix room has been created for community discussion about the mobile apps. The mobile apps also receive design support from Morphymore who currently produces UI mockups. 

- Privacy support, some work already completed here, https://github.com/planetdecred/dcrandroid/pull/520
- Politeia viewing and notifications, https://github.com/planetdecred/dcrandroid/pull/503
- Staking, supported in dcrlibwallet for godcr, and can be reused on mobile, https://github.com/planetdecred/dcrlibwallet/pull/163
- Coin control input selection features
- Dark Mode for the UI
- Password input delay to resist brute force attacks
- Including the mobile apps in other apps stores.
- Direct APK download with signatures, planned for the coming v1.6 release.

### Details
Work will be being performed mainly by Raedah Group with product management done by Raedah. Android developers are Collins and Dreacot. iOS developers are Macsleven, Justindo. Dcrlibwallet maintainer is Collins, with peer review often coming from members of the GoDCR development team who are also using dcrlibwallet. Design mockups will come from Morphymore. Work will be done by developers based on availability. Work from Sept 2020 and Oct 2020 will be billable under this proposal, and 6 months forward from Nov 2020 through April 2021. An allocation of $5500 per month, covering 8 months for this proposal, with a proposal billing limit of $44,000 USD. This budget has been created based on average ongoing costs with additional allowances allocated to allow for other developers to join our efforts.