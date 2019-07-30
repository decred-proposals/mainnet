TinyDecred: A Python Toolkit for Decred


My name is Brian (@buck54321 on github). I've been a Decred contributor for 
about a year and a contractor almost as long, working mostly on dcrdata. 
I've developed a set of tools for working with Decred in the Python programming 
language, and I want these tools to grow under the control of the Decred 
stakeholders and with the expertise of our development community. The package is
called TinyDecred. Browse the repo
[here](https://github.com/buck54321/tinydecred).

### Executive Summary

The core of the offer is a repository of code structured as a set of programming 
tools, or Python "modules". 
These tools enable Python developers to easily add support for Decred into their 
applications.

The anticipated benefit for Decred stakeholders comes primarily from exposure to
the relatively large pool of programmers who use Python, and from the potential 
for integration into wallets and other blockchain products.

The code itself will be transferred to a repository under the Decred 
organization. Further control will be transferred to the stakeholders and senior 
developers, though I plan to keep working on the project.

### Why?

Python is a phenomenally popular programming language. In a search for
"most popular programming languages", you'd be hard-pressed to find a list 
in which Python is not in the top five. 
[Github's Octoverse Report](https://octoverse.github.com/projects) ranks it at 
number 3 in popularity. Blockchain is not foreign to Python developers either.
The [Electrum Wallet](https://electrum.org/), for example, is written in Python. 
There are well-developed Python libraries for a number of popular blockchain 
projects 
[[bitcoinlib](https://github.com/1200wd/bitcoinlib), 
[eth/web3.py](https://github.com/ethereum/web3.py)], 
and Python is a common choice for tutorials that introduce programmers to the 
concepts of blockchain.

Making inroads into this development space exposes Decred to an as-yet untapped
pool of talent and innovation. It provides entry points for new developers, and 
has the potential to get Decred integrated into more wallets, websites, and 
apps of all shapes and sizes.

### What do you get?

The full repository will be transferred to the Decred organization, where 
development will continue under stakeholder control. 
As a Decred project, TinyDecred will enjoy all the benefits and suffer all the 
scrutiny associated with official Decred projects. 
I would continue working on the project, but would be subject to removal from 
the project at the discretion of senior developers and ultimately stakeholders. 
That said, I'm into this thing, so expect support and development from me for 
the forseeable future. 

### Package Details

This section is technical in nature.
If that's not your thing, feel free to skip it. 

The TinyDecred package contains modules supporting the following features.

- A **pure-Python secp256k1 elliptical curve**. For generation of key pairs
  and ECDSA signature creation and verification. 

- **BIP-0044 keys. Account creation and management. PGP mnemonic seeds**. 
  Enables multi-asset support for hundreds of currencies including 
  Bitcoin, Ethereum, Ripple, Litecoin, and virtually all other the major coins, 
  all from a single master key.

- **Clients for the dcrdata block explorer** (websockets, pubsub, data API, 
  Insight API). In addition to making the entire blockchain's data easily and 
  quickly accessible, dcrdata is needed by basic light wallets to broadcast 
  transactions and sync UTXOs.

- **Serializable and de-serializable Python versions of important types from the 
  dcrd/wire package**: Enables   blockchain data to be stored with minimal disk 
  space and shared with the   Decred network and compatible software. `MsgTx`, 
  `BlockHeader`, `OutPoint`, etc.

- Pythonized **network parameters for mainnet, testnet3, and simnet**. Used 
  extensively throughout TinyDecred and certain to find value in any 
  Decred-supporting Python project.

- **TinyDecred wallet**. An experimental PyQt5 GUI wallet. 
  Already has basic light wallet functionality, and working towards staking. 
  Initially, the wallet is more for demonstration of the module features, but
  designed to grow into a full-fledged product. 
  Would love to work on SPV, multi-asset, Decred DEX, and lightning network. 

A nice feature of this package is that it has no dependencies outside of
the Python Package Index (PyPI or `pip`). Most implementations of the secp256k1
curve in Python require a specific version of OpenSSL C library to be installed, 
but the curve in TinyDecred is implemented from scratch. That means that once
TinyDecred is made available through PyPI, it can be installed with all 
dependencies as simply as `pip install tinydecred`. 

The code is modeled after code in the core Decred projects, so implementation of 
new features proceeds in a straightforward way. 
In fact, much of the code shares variable and function names and even many 
comments and docstrings with the golang versions. 
Coincidentally, golang and Python share some important syntax conventions, such
as indentation, that make copy-paste -> translate-in-place a bearable experience.

There are other Python packages that implement parts of the same functionality 
([ecdsa](https://github.com/warner/python-ecdsa) has secp256k1 and 
[bitcoinlib](https://github.com/1200wd/bitcoinlib) has wallets), but they aren't 
built on Decred from the ground up and there are Decred features that would be 
non-trivial to add, e.g. staking, lightning, SPV. Implementation of these 
features in TinyDecred is greatly simplified by the code mirroring discussed 
above.

I'll leave the code reviews up to others, but will just say that I've made every 
effort to keep the code clear, concise, and extensible. 
Functions and classes are documented and commented throughout. 
Test coverage is good in the low-level modules, and getting better in the 
dependent modules. 

### What's with the name?

The name *pydecred* seems like an obvious alternative, but *pydecred* is 
actually a module within TinyDecred. The name TinyDecred is taken from the 
name of the wallet, which depends not only on Decred-specific code such as that 
in the *pydecred* module, but also on some more general-purpose modules.

The TinyDecred wallet is a system tray app. The window that it opens is small.
The *tiny* part means unobtrusive. Planned development would enable 
TinyDecred to run a full or SPV node, and it's nice not to clutter up your 
taskbar/dock with persistent but low-interaction applications. 
The low-profile, always ready system tray app and small window are also 
reflective of a guiding philosophy for TinyDecred development:
*Decred should be an omnipresent yet largely invisible part of our digital 
environment, and using Decred should be as simple as pulling change out of your 
pocket.*

### What's the offer?

I have not charged as a contractor for this work, which comprises more than 
15,000 lines of new code and docs, tests, iconography, etc. I actually 
never intended to create a public-facing package. I was just trying to explore 
and learn about Decred by coding. But I got carried away and ended up with 
something I think has value to the Decred community. How much value, you ask? 
I'm hoping at least $8,000 worth. The costs are predicated on more than 2 months 
of full-time equivalent work. In an hour-for-hour comparison, this is a 
substantial reduction to my typical contractor rate. 

### Price: $8,000

[Browse the TinyDecred repo](https://github.com/buck54321/tinydecred)