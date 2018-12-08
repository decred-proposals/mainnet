Decred Bug Bounty Proposal
# Decred-Bug-Bounty-Proposal

# What:

I suggest we start a bug bounty program to find security vulnerabilities in decred. This would help us improve our overall security posture and get a fresh set of eyes on our code and websites.


# Why:

We do not currently have a formal bug bounty program. A bug bounty program aims to use collective intelligence of many "bug bounty hunters" to find and fix security vulnerabilities. 

Many times I observe people visiting our chatrooms and inquiring about a bug bounty program which shows there is a real interest in people who want to find vulnerabilities in decred and report them for an award.Having a formal program will enable us to funnel all reports through one single process and ensure that valid reports are looked at and fixed  while keeping away bad reports that take up valuable dev time.

# How:

We will have a selfhosted program and use a @decred.org email for getting bug bounty reports.The bug bounty hunters will be sending us PGP encrypted emails of their findings in a predefined format. 



1. We will be using the OWASP Risk Rating Methodology for scoring and prioritizing vulnerabilities (https://www.owasp.org/index.php/OWASP_Risk_Rating_Methodology)

2. We will also take into consideration the impact on the decred ecosystem. An RCE in dcrdocs (Low impact) is not the same as an RCE in dcrd or decrediton (Higher impact)

[OWASP Risk Rating Methodology](https://raw.githubusercontent.com/degeri/Decred-Bug-Bounty-Proposal/master/owasp.png)



Indicative payout amounts:

Note: up to 300 USD 

Low: up to 1,000 USD

Medium: up to 3,000 USD

High: up to 10,000 USD

Critical: up to 25,000 USD



To achieve all this we need a group of "vulnerability validators" who are verified decred contractors. Their jobs are as follows.

    - Check, validate and respond to all bug reports sent to the system.

    - If its a serious vulnerability escalate the vulnerability to the person in-charge of the project and core staff.

    - If its a non serious open an issue in github and follow through on fixes.

    - Maintain constant contact with the bug reporter and keep them apprised on the status of their report.(Many times I see frustrated bug reporters complain on twitter or publicly release 0-day bugs due to security teams not responding properly to their reports) 

    - Form a core team that decides on any payout above 500$. (Anything below this can be given out at their discretion)
  

* We will need to do some social media posts to get the word out.

* We need to define the bug bounty policy/rules and scope.

* Setup a simple website bounty.decred.org which will contain information about the program,rules and scope.

* Setup a "Thank you" page in the "bounty.decred.org" website to publicly appreciate the people who have found valid vulnerabilities.


**Who:**

* I have been working with the decred project the last few months and would like to believe I have contributed in a useful manner to decred. I also have prior experience as both a bug hunter and a validator and think I would be a good fit for this role.  Hence I nominate myself as a validator for this project.


Current Validator List: dnldd, Degeri (me), matheusd, jholdstock

Website Development: fernandoabolafio, Degeri (me)

**Costing and Funds:**

* The DCR for this project will stay with the treasury and we send them monthly requests to release the funds directly to the bug bounty hunters Decred address or towards operation costs if any. 

* The validators who will already be contractors of decred and can bill the decred project directly for hours spent on this work.

* I don't see each validator spending more than 20-30 hours a month. 

**Cost Breakdown**


*An operating budget of **5,000 USD** for six months.*

This will cover the following:

   - Setting up and Maintaining the bounty website.  (2,000 USD)
    
        Breakdown:
        
        5 Hours x 7 Days = 35 Hours x 40usd/hour = 1,400 USD for Web Development 
        
       200 USD completion bonus
            
        10 Hours * 40usd/hour= 400 USD for any other minor edits during the 6 months.
        
   -  Defining policies/rules and scope (1,000 USD)
  
  -  Anything other non bounty expenditure like setting up email system, book-keeping etc . (2,000 USD) 


Since we cannot predict the types of vulnerabilities and their severity it is not possible to have a fixed payout limit. But based on past trends and other bug bounty programs I predict that this would not cross **100,000 USD for 6 months**.

Note: (Since we suggest the treasury spend the money directly any excess will be available for other proposals and spending) 

**When and Duration:**

 * I suggest we plan to get this up for vote in one week. And launch the bug bounty project by the last week of December or January first week.

 * This project would be approved for 6 months the end of which I will compile a detailed report for the community and if all goes well request for another 6 months extension using a revised proposal. 

**Work Flow**

[WorkFlow](https://raw.githubusercontent.com/degeri/Decred-Bug-Bounty-Proposal/master/workflow.png)


Below is a sample programs rules and scope:

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


**Introduction:**


The decred community welcomes security researchers and bug bounty hunters to find security vulnerabilities in its website and projects. (more text to follow). All bug reports need to have a clear exploit or POC. 

**The following domains  in scope:**

*.decred.org

*.dcrdata.org

**The following domains are not in scope:**

https://slack.decred.org/ (Slack)

https://alpha.dcrdata.org (dcrdata alpha site)

++add more later

**Projects in scope : **

The following active projects under (https://github.com/decred/) :

dcrdata

decrediton

politeia

politeiagui

dcrdata

dcrstakepool

dcrweb

dcrdocs

(More will be added in the actual bounty website)



**The following vulnerabilities are generally out of scope:**

* Missing security best practices that do not directly lead to a vulnerability

* Insecure settings in non-sensitive cookies

* Vulnerabilities (including XSS) that affect only legacy browser/plugins

* Non-technical attacks such as social engineering, phishing, or physical attacks against our members, users, or infrastructure

* Missing HTTP headers, unless a vulnerability can be demonstrated

* Bugs requiring exceedingly unlikely user interaction

* Clickjacking on pages with no sensitive actions.

**Rules:**

* We prohibit DDOS or network bandwidth load testing.

* Unfortunately we are unable to pay for duplicate reports 

* Public disclosure of the vulnerability without prior approval will make it ineligible for bounty.

* No social engineering.

* No spamming.

* All Current/Past (For up-to 6 months) decred developers are barred from taking part in this bug bounty program. 

* Vulnerability reports made before the start of the program will not be eligible for a bounty.

**Reminders:**

* Almost all of decred's projects can be run locally and reproduction instruction are available on github. We strongly recommend you to do this.

* Only test the code in the "main" merged branch of the projects.

* Use the testnet when possible.

* Decred project is not responsible for any loss of DCR due to bug testing. (ie: don't do dumb stuff and lose your DCR)
