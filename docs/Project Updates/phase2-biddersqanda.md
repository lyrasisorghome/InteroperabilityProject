# Phase 2 Implementation - Bidders Questions and Answers

## Contractors outside the U.S.
**Question:** Can Lyrasis contract with an individual working outside the U.S.? If so, what vendor documents do you need?

**Answer:** Lyrasis can contract directly with an individual working from any country U.S. organizations are legally allowed to do business with. International contractors are required to complete a [w-8ben](https://www.irs.gov/forms-pubs/about-form-w-8-ben) or [w-8ben-e](https://www.irs.gov/pub/irs-pdf/fw8bene.pdf) form and are responsible for the payment of all taxes, including VAT, etc.
___

**Question:** Is Lyrasis registered with any foreign tax entities?

**Answer:** Lyrasis will not collect any foreign taxes. Bidders are responsible for all applicable taxes and must take that into account in the quote.  
___

## References
**Question:** For references may I list open-source maintainers who reviewed my work, or do you require past clients?

**Answer:** For references you may list open-source maintainers who have reviewed your work.
___

**Question:** If the bidder's team members have worked on private code, would you accept profesional references who supervised or worked with the proposed team members in previous roles?

**Answer:** Yes, professional references for closed code would be acceptable.
___

## Licenses
**Question:** For the public-code requirement would a new openly-licensed demonstration be acceptable alongside descriptions of our products?

**Answer:** All outputs from this project must be made available under the open license that is used by the application.
___

**Question:** May bidders include an independent QA subcontractor for that work, and is there a public way to connect with teams preparing a bid?

**Answer:**  We will not be accepting quotes for independent QA subcontracts. The bidders information session was an open venue to connect.
___

**Question:** For prior work, if a relevant project’s code is private under a client agreement, may bidders describe it
and offer a live walkthrough instead of a public link?

**Answer:** For private code, please provide a client reference.  Providing supplementary materials, such as a video recording of a walkthrough of an application with private code is acceptable, but doesn’t substitute for the client reference.
___


## Implementation Details

**Question:** For the Work Package C VIVO SWORD deposit proposal, may the implementation lead name a separate subcontractor to prepare fictional publication records with expected VIVO-to-repository metadata mappings, then check that the administrator guide matches the accepted configuration? Would you want that bounded scope shown under the acceptance-test milestone or separately in the team and cost breakdown? The lead would retain responsibility for implementation and final submission.

**Answer:** This should be shown in the team and cost breakdown.
___

**Question:** For the Work Package C VIVO SWORD deposit proposal, given that  VIVO is natively based on RDF/OWL ontologies and SWORD 3.0 offers a significant architectural advantage through its support for JSON-LD, would Lyrasis consider a proposal based on SWORD 3.0 rather than SWORD 2.0, including the necessary adaptations on the DSpace side?

**Answer:**  While it would be ideal if we could target SWORD 3.0 from the outset, it is not widely adopted, and most importantly, not in DSpace, which still only supports SWORD 2.0.
___

**Question:** if Work Packages A and B are awarded to one vendor and C to another, how will the vendors coordinate? The A3-4 specification describes V1 as its sibling deposit design, so we’d like to understand how Lyrasis would keep the two aligned, for example through shared check-ins or a Lyrasis coordinator.

**Answer:** There is not a specific requirement that the design and implementation for the SWORD feature for A3-4 and V1 be kept aligned. That said, we will create a Slack channel for vendors working across projects to communicate if they want, and all work will be done in public repositories, so that the teams can follow each other’s work.  In addition, the project lead will be monitoring all work and will share relevant information across when applicable.
___
**Question:** At the information session we asked what should happen when a linked DSpace item is withdrawn, made private or deleted (or the linked ArchivesSpace record is deleted or moved), and were advised to call this out as a gap in our proposal. Should we treat its handling as part of the core Work Package A scope, or as a separate optional item?

**Answer:** Please handle the case of a linked item being withdrawn or deleted as a separate optional item.
___
**Question:** A1-2 uses one shared DSpace service account for search. Should results inside ArchivesSpace exclude restricted or embargoed items the archivist could not normally see in DSpace?

**Answer:** This is an implementation detail that may need to be worked out with the ArchivesSpace team.  For the purposes of the quote please account for issues like this is in any risk padding you provide.
___
**Question:** A1-2 reuses an existing Digital Object when its digital_object_id matches the DSpace URI. Many sites already hold hand-entered DSpace links in other forms, such as hdl.handle.net addresses or /items/ URLs. Should those be recognized as the same item, or is exact matching enough?

**Answer:** This is an implementation detail that may need to be worked out with the ArchivesSpace team.  For the purposes of the quote please account for issues like this is in any risk padding you provide.
___
**Question:** To decide between a plugin and a core change, what will the ArchivesSpace program weigh most, for example release timing, long-term maintenance ownership, or deployment on hosted sites?

**Answer:** The question of whether A1-2 linking feature is a plugin or core code will be decided jointly between the implementer and the ArchivesSpace team based upon various factors.  If the decision will materially impact your anticipated costs, we recommend indicating that in the proposal and providing separate quotes for both approaches. 
___
**Question:** Deposited files pass through ArchivesSpace on their way to the repository, with a default per-file cap of 100 MB. For Lyrasis-hosted ArchivesSpace sites, are there hosting limits we should design around, such as upload size, outbound connections or request timeouts?

**Answer:** Please assume that any file-size limits, number of outbound connections and request timeouts should be configurable by whomever deploys ArchivesSpace.  
___
**Question:** G-15 asks the implementation team to confirm details with a VIVO subject-matter expert. Can Lyrasis help connect the selected vendor with one? And before the proposal deadline, may bidders speak with VIVO users or researchers, for example through short usability interviews?

**Answer:** Lyrasis will connect the implementor with the appropriate VIVO community members during implementation.  You are welcome to reach out to the community ahead of time through their public channels while working through your proposal.
___
**Question:** V1 recommends JavaClient2.0 but notes its coordinates are “TBD” and “may require vendoring or JitPack,” and plans an Epic 0 spike to prove the dependency. If that spike shows the library is hard to bring in, would Lyrasis be open to a small native HTTP client behind the same adapter, as A3-4 recommends for the Ruby side?

**Answer:** Yes that is a reasonable assumption.
___
**Question:** Once the awarded Work Package or Packages are complete, would there be a maintenance or support period after the M6 release and handoff?

**Answer:** If you want to include a quote for post-handoff maintenance or support you are welcome to, although this is not required and may not be funded.  The goal is for the final milestone hand-off to be sufficient for the community to assume responsibility for the code post hand-off.
___
**Question:** The RFP specifies WCAG 2.2 AA, while the session slides mention WCAG 2.1 AA. Will any third-party vendors be involved in accessibility and compliance testing?

**Answer:** Apologies for the discrepancy in WCAG versions . Confirming that WCAG 2.2 is the target. The communities use automated tools to test for accessibility, but we will not be conducting a separate 3rd party audit. 
___
