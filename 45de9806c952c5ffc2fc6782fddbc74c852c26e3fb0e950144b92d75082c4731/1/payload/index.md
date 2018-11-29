Add Decred support to Coffee Wallet
**What**

Add Decred support to Coffee Wallet.

https://wallet.coffee/

What makes Coffee Wallet different from other multi coin wallets is that it integrates a "portfolio" functionality. This makes it useful as a blockchain front-end that does not force user to trust a single piece of software with all his assets. User can store his wallets in a secure location like a hardware wallet, have some tiny amounts to use on the go, and see value of both live. It aims to educate user on safe blockchain usage (not to keep all his keys on an exchange for instance)  

Another important feature is "send via message" which allows user to send crypto currency via SMS / Messenger etc. Imagine two friends sharing coffee. The one that is not using crypto yet pays with fiat cash and the other pays him back using DCR with a single text message. It helps adaptation and show to the newcomer how crypto currencies can be used as a store of value.

Short whitepaper with more info: https://wallet.coffee/whitepaper.pdf


**Why**

At the moment, Coffee Wallet can be used to track Decred portfolio but I would like to implement DCR wallet support.

This will allow to add another entry in "3RD PARTY WALLETS" section on https://decred.org/downloads/ with this open source, multi platform application.

Coffee Wallet is in beta and before marketing stage so this will not bring any large user base but in the future all new Coffee Wallet users will see DCR on a list of fully supported currencies.


**How**

Coffee Wallet uses bitcoinjs-lib to generate keys and sign Bitcoin transactions. This library can be used to:
* Generate Decred private/public key from user 12-word mnemonic.
* Sign transactions and sent them to Decred's Insight at https://mainnet.decred.org/tx/send

Budget of 150 DCR will be sufficient for this and any leftovers will be used to promote news with "Coffee Wallet version X with Decreed support".


**Who**

Myself, Franciszek Wawrzak, founder and developer of Coffee Wallet.

**When**

Ideally this could be implemented in upcoming release and released early January 2019.


I would be glad to answer any questions and hear any suggestions.
