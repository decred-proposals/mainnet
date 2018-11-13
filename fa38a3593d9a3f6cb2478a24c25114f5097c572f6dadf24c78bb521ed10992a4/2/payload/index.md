Decred Contractor Clearance Process
### Abstract

Open source projects often employ informal methods for implementing quality control on the contributions of their developers, e.g. the judgments of key project members.  Rather than continuing to rely on an informal system for vetting Decred contractors, prospective Decred contractors would undergo a standard process to obtain a Decred Contractor Clearance (“DCC” for short) before being eligible to bill the project for their work.  A DCC would be required not only for contractors, but any subcontractors they are billing for.  This means corporate contractors will need to get each person working for them individually cleared.

The process for obtaining a DCC would require that 3 existing contractors in a given subdomain vouch for the applicant’s work or skills.  Similarly, stripping a DCC would require that 3 existing contractors in a given subdomain testify that the contractor should have their DCC revoked.  The overall contractor group would have the ability to override the issue or revocation of DCCs with an all-contractor vote, weighted by average hours worked per month for the project for each individual contractor.  In the case of particularly contentious disputes, it is possible to escalate such a dispute in a proposal, to be resolved by the stakeholders.

In the specific case of software development, the DCC process will involve some amount of open source code being written for one of our repositories and reviewed by existing development contractors.  Other subdomains besides development will have their own processes, e.g. share a portfolio or generate marketing deliverables, and these can be made more formal in the future.

### Motivation

Maintaining quality control on the various subdomains that make up Decred is a problem that many open source projects have to deal with.  While an individual developer may be very talented, most open source projects of substance would have serious problems with that same talented developer forming a corporate entity, submitting a bunch of code from people they hired, and there being no quality control processes for the submissions.  Since our project spans multiple subdomains, this same problem is present in contexts outside the development process, e.g. marketing and design.  Conventional corporate entities deal with quality control via their hierarchical decision making infrastructure, but that is necesssarily a centralized process and does not map well onto Decred.

Having 3 contractors in a subdomain vouch for the issuance or revocation of a DCC forces those contractors to have skin-in-the-game when it comes to staffing decisions.  Contractors can be held accountable for their staffing decisions, good or bad, which will lead to better staffing decisions over time.  It is ideal for these 3 contractors who vouch for an issuance or revocation to not be from the same corporate entity, whenever possible, and, more generically, to be independent of one another.  Auditing these DCC issuance and revocation proposals for conflicts-of-interest will be an ongoing task.

The all-contractor override for issuing and revoking DCCs is meant to handle edge cases where there is a conflict within a subdomain, e.g. two or more groups within a subdomain fighting for influence.  Such internal conflict is obviously bad for the project, and when necessary, there needs to be a dispute resolution mechanism to prevent malicious behavior on part of these groups, e.g. attempting to revoke their opponents’ DCCs.  If a DCC revocation has been initiated against a contractor and it is a dispute is of a sufficient scale, importance, and contention, the matter may be raised as a proposal for stakeholder to resolve by voting.  By allowing contractors to settle matters amongst themselves, it avoids having staffing issues becoming stakeholder popularity contests.

All-contractor votes should be weighted by the hours billed by each contractor over a period, say 6 months.  The weighting here would reflect the added skin-in-the-game that full-time contractors have relative to part-time contractors.  These votes would be made by individual DCC holders, not the corporate entities they work for.

### Implementation

To transition from our existing informal contractor system, existing contractors would be granted a DCC for their respective subdomains.  The DCC process would begin once the initial contractor management system is complete.

Project-related work performed prior to a DCC issuance by a propsective contractor can be billed for after the DCC is issued.

Milestone 1: add support to contractor-mgmt for DCC issuance and revocation proposals, with the 3 contractor support requirement, but without the all-contractor or stakeholder overrides

Bonus 1: USD 5,000

Milestone 2: add support to contractor-mgmt for all-contractor votes, weighted by hours worked per individual contractor in the past 6 months

Bonus 2: USD 5,000

Milestone 3: add support to contractor-mgmt for escalating to a proposal and corresponding stakeholder vote

Bonus 3: USD 2,000

### Contractors

The initial contractor list is Sean Durkin, Marco Peereboom, Alex Yocom-Piatt and Luke Powell.

### Timeline

Milestone 1: within 3 months

Milestone 2: within 6 months

Milestone 3: within 7 months

### Projected Cost

Estimated total cost is USD 25,000 in labor and USD 12,000 in bonuses.