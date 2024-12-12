# Contributing to the RFC Process

Thank you for your interest in contributing to our RFC process! This document outlines how you can propose new RFCs, review others' proposals, and help improve the evolution of our projects and practices.

## What is an RFC?

An RFC (Request for Comments) is a standardized way to propose significant changes to our codebase, project processes, or policies. RFCs are intended for changes that require input and consensus from a broad group of stakeholders, including leaders, contributors, and the team.

## Before You Begin

1. **Check Existing RFCs**: Review the `text/` and `drafts/` directories and open Pull Requests (PRs) to ensure a similar idea hasn’t already been proposed or accepted.
2. **Discuss Ideas Early**: If you’re uncertain about the viability of your proposal, consider starting an Issue or raise it in Discord channel to gather initial feedback before investing time in a full RFC.

## Proposing a New RFC

1. **Fork and Clone**:  
  Fork this repository and clone it locally.

2. **Create a New Draft File**:  
   Copy the template file `0000-template.md` and rename it to something descriptive, for example: `drafts/0000-my-feature-proposal.md`.  
   Do not assign a number yet if you’re unsure—just use `0000` and a descriptive title. The number will be finalized when the RFC is accepted.

3. **Write the RFC**:  
Fill out each section of the template thoroughly. Provide as much context and rationale as possible. Include the following:
- **Summary**: A concise description of the proposal.
- **Motivation**: Why this change is needed and what problems it solves.
- **Proposal**: Technical or procedural details about how the change would be implemented.
- **Drawbacks and Alternatives**: Potential downsides and other approaches considered.
- **Adoption and Migration**: Steps for transitioning from the current state to the proposed future state.
- **Definition of success**: How do we know if this proposal was successful? Are there any metrics we need to start tracking?


4. **Open a Pull Request**:  
Once your draft is ready, open a new Pull Request in this repository with the title: `RFC: <Your Proposed Title>`.  
In the PR description, summarize your proposal and link to any relevant issues or background discussions.

5. **Engage in Review**:  
Expect to receive feedback from other members and leaders. Be prepared to revise your RFC multiple times. Updates should be pushed to the same branch, keeping the discussion in the same PR.

## Reviewing RFCs

1. **Be Constructive and Respectful**:  
Focus on the proposal, not the person. Offer concrete suggestions, point out ambiguities, or raise concerns about feasibility.

2. **Ask Questions and Seek Clarity**:  
If something is unclear, ask the author to clarify. Constructive dialogue often leads to a stronger, more refined proposal.

3. **Consider Long-Term Impact**:  
Look beyond immediate usefulness. Consider maintainability, complexity, potential regressions, and how the change aligns with our long-term goals.

4. **Reach Consensus**:  
The goal is to improve the RFC until it’s either accepted or deemed not beneficial. If significant objections remain unresolved, the RFC may be rejected or asked to return to a draft state.

## Acceptance and Merging

- **Acceptance**:  
Once members and leaders reach consensus, a leader will update the RFC’s number (if needed) and move it into the `text/` directory. The PR will then be merged.

- **Rejection or Withdrawal**:  
If an RFC does not gain traction or does not address core concerns, it may be closed. Authors can always revisit and resubmit at a later date if circumstances change.

## Post-Acceptance Follow-Up

After an RFC is accepted:

- **Implementation**:  
If the RFC suggests code changes, the next step is implementing them in the main code repository. The RFC may reference upcoming issues, PRs, or project plans.

- **Documentation and Communication**:  
Accepted RFCs serve as a historical record. They may be referenced in documentation, announcements, or as guides for future contributors.

## Frequently Asked Questions

**Q: Do I need approval to submit an RFC?**  
A: No. Anyone is free to propose an RFC. However, team members input and leaders approval are required for acceptance.

**Q: How long does it take for an RFC to be reviewed?**  
A: It varies. Some simple proposals may be quickly accepted, while complex ones may require extended discussion.

**Q: Can I propose changes to this RFC process itself?**  
A: Absolutely! Improvements to the RFC process are welcome. Simply submit an RFC proposing the changes you’d like to see.

---

Thank you for helping shape the future of our projects through thoughtful, collaborative RFC proposals. Your contributions are valued and appreciated!
