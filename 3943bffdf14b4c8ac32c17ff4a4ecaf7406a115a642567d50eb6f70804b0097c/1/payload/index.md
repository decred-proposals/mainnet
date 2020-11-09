Decred Address Scanner

**What is it?**

A lightweight app that can track decred addresses on android. It has already been in the [google store](https://play.google.com/store/apps/details?id=com.joegruff.decredaddressscanner) for over a year with 500+ downloads and is already [open source](https://github.com/JoeGruffins/dcraddrscanner) on github.

This proposal aims to get the source code into the decred repository and a little more developed.

**Why do we need this?**

For me at least, the app has been extremely useful in tracking when tickets have voted. I get a sound and visual notification on my phone. This is something that I have heard a lot of people asking for. It would be great to make the app "official" and get more eyes on it, as I think it greatly improves the staking experience.

Of course it can also be used to observe any arbitrary address, such as the treasury address. One could also use it to be notified of a payment in dcr... if such things happen.

**How does it work?**

It works by connecting to a block explorer and retrieving data for an address. Addresses can be input via the clipboard or scanning a qr code. Addresses can be given aliases and are saved in a very simple address book until deleted. On the device, the addresses are saved in an app-specific database and cannot be accessed by other apps. Addresses can further be starred. Starred addresses will be checked for changes every 30 or so minutes, and the user is notified upon any change of amount.

**And what do you want?**

3000 usd - arrears

I am asking for 3k usd in arrears for development thus far. From a "time spent" perspective this is too little, but I was still learning at the time, and it lead to greater things.

6000 usd MAX - updates, features, and bug fixes (no currently known bugs exist)

Explained in updates and features sections. This will be paid to contractors delivering good code/reviews at their hourly rate. **Any unused funds will remain unused.**

TOTAL 9000 usd

**Needed updates**

Two areas really need updates. One is the infrastructure. This app was originally built for android 27 (I believe) and now android is at 30. I recently tried to update and found many things broken. Perhaps the biggest barrier to updating is the rather hackish qr code reader, which is the second most needed update. Some googling has lead me to some good looking alternatives that should be much easier to implement and update in the future. Of course only open source and freely licensed modules will be used.

It must also be noted that the app in the play store currently displays a donation address when clicking the top right corner. **This will be removed!** It is already removed in the code. It still exist in the google play store because I must update the target api (currently 27) in order to upload. And as I said, just updating looks to be quite a task. Because there have been zero donations to date, I hope that this is not an issue.

After updating I want to spend some time refactoring and creating proper documentation. Then the repo at that state will be thoroughly reviewed by other contractors (hello @itswisdomagain) and added to the decred.org repositories. After that I want to get in a few features that I think are needed.

**New features**

scan a tx - One feature that I think would be good for stakey is the ability to scan/paste a txid and pull out the commitment address (where the money goes), so anyone can point and click to watch a ticket.

choose explorer - While the default as dcrdata is fine, it would be good to allow someone to specify their own, or a different block explorer. This would allow for a completely closed system if one wanted, although dcrdata is perfectly safe, don't get me wrong. It would also allow the app to be used on testnet by pointing it at a block explorer running on testnet.

**What's the timeline?**

It will be done within four months from approval  (if approved).

**Then what?**

That's it for now, for this proposal, unless I have some requests for more utility. The app has been stable with minimal maintenance for over a year now, so I don't think constant updates are necessary. Upkeep costs should be minimal.

**Who will do this?**

Me, Joe, and other decred contractors who wish to contribute. I have been a decred contractor for over a year and have commits in many of the repos, including dcrd, dcrwallet, decrediton, dcrdex, and tinydecred. My github is @JoeGruffins. I live to serve the stakeholders.