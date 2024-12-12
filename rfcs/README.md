# RFCs

This directory hosts all **Request for Comments (RFC)** documents for NgheNhan platforms (trading platform, funds management). RFCs provide a structured, collaborative process for proposing, discussing, and accepting significant changes to our projects, policies, and practices.

## What is an RFC?

An RFC is a proposal for a substantial alteration or addition to our technical direction, design, architecture, or project processes. By proposing an RFC, you’re asking the team to consider a change, comment on it, and ultimately reach a consensus on whether to adopt it.

**Examples of when to submit an RFC:**
- Introducing a major new feature or subsystem.
- Deprecating or removing an existing feature.
- Changing core architectural patterns or libraries.
- Establishing new coding standards, tooling conventions, or documentation policies.

## Directory Structure

rfcs/
├─ README.md // This file, explaining the RFC process 
├─ CONTRIBUTING.md // Guidelines for proposing and reviewing RFCs 
├─ text/ // Finalized (accepted) RFCs 
├─ drafts/ // (Optional) Under-review or draft RFCs 
└─ 0000-template.md // RFC template for new proposals


- **`text/`**: Contains all accepted RFCs, each assigned a unique number and descriptive name, e.g., `0001-improve-build-system.md`.
- **`drafts/` (optional)**: Contains RFCs currently under active review or not yet accepted. Once accepted, an RFC is moved and renumbered into `text/`.
- **`0000-template.md`**: A template file you can copy and modify to start a new RFC.

## RFC Lifecycle

1. **Proposal (Draft)**: A contributor copies `0000-template.md`, renames it, and edits it to describe their proposal. They then open a Pull Request (PR) in this repository.
2. **Discussion**: Team members and leaders leave comments and suggest changes. Feedback should be constructive and focused on the RFC’s goals and feasibility.
3. **Revision**: The RFC author may update the proposal based on feedback. The goal is to reach a consensus on a solid approach that the project is willing to maintain.
4. **Acceptance or Rejection**: After a sufficient review period and discussion, the leaders or core team will decide:
   - **Accepted**: The RFC is renumbered (if needed) and moved to `text/`. The corresponding PR is merged.
   - **Rejected or Withdrawn**: If no consensus can be reached or the idea no longer seems viable, the RFC is closed and/or marked as rejected.
   
**Note:** Accepted RFCs become part of our project’s historical record and can guide future improvements or serve as a reference point.

## How to Contribute

1. **Check Existing RFCs**: Before proposing a new RFC, review the current `text/` and `drafts/` directories. Your idea may already be in discussion.
2. **Create a New Draft**: Copy `0000-template.md` and rename it using a descriptive title. For example:  
   `drafts/0000-new-build-system.md`
3. **Open a PR**: Submit a Pull Request with your draft RFC. Provide a summary in the PR description, linking to relevant issues or discussions.
4. **Gather Feedback**: Engage constructively with reviewers. Incorporate their suggestions to improve clarity, correctness, and feasibility.
5. **Reach Consensus**: Once the team is in agreement, a leader will approve the RFC. The file will be moved to the `text/` directory with a new number (e.g., `0001-new-build-system.md`).

## Review Expectations

- **Timeliness**: We aim to respond to new RFC proposals within 1-2 days.
- **Respect & Professionalism**: Healthy debate and differing opinions are encouraged, but personal attacks or disrespectful behavior will not be tolerated.
- **Decision Making**: The final call to accept or reject an RFC rests with the project’s leaders. Their decision will be based on technical merit, long-term sustainability, project impact, and alignment with the project’s goals.

## Frequently Asked Questions

**Q: Do all changes need an RFC?**  
A: No. Small adjustments, bug fixes, and minor improvements can be done via normal pull requests. Use RFCs for significant shifts or additions that require broad consensus.

**Q: How long does the RFC process take?**  
A: It varies. Some RFCs may be simple and reach acceptance quickly, while others may require prolonged discussion.

**Q: Can I propose changes to the RFC process itself?**  
A: Yes. If you have suggestions for improving the RFC process, submit a new RFC proposing those changes!

---

Thank you for helping shape the future of NgheNhan through thoughtful, collaborative proposals.

