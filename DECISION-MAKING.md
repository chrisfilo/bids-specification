# BIDS Decision Making Process

* [Introduction](#introduction)
* [Definitions](#definitions)
* [Principles](#principles)
* [Merge requirements](#merge-requirements)
   * [Low impact](#low-impact)
   * [Medium impact](#medium-impact)
   * [High impact](#high-impact)
* [Process for a vote on high impact pull requests](#process-for-a-vote-on-high-impact-pull-requests)
* [Additional notes](#additional-notes)

## Introduction

The Brain Imaging Data Structure (BIDS) community set out the following
decision-making rules with the intention to:

- Strive for consensus.
- Promote open discussions.
- Minimize the administrative burden.
- Provide a path for when consensus cannot be made.
- Grow the community.
- Maximize the [bus factor](https://en.wikipedia.org/wiki/Bus_factor) of the
  project.

The rules outlined below heavily depend on the
[GitHub Pull Request Review system](https://help.github.com/articles/about-pull-requests/).
If you have any questions - both in terms of the technical logistics of using
GitHub to submit your review or to clarify how the steps described below are
implemented in practice - please first
[review the contributing guidelines](CONTRIBUTING.md) then
[open an issue](https://help.github.com/articles/creating-an-issue/).


## Definitions

The following terms have a specific meaning in this document and are
defined as follows:

* **Repository**: [https://github.com/bids-standard/bids-specification](https://github.com/bids-standard/bids-specification)

* **Contributor**: anyone who has contributed to the BIDS community. A list of
contributors can be found in
[src/99-appendices/01-contributors.md](src/99-appendices/01-contributors.md).
  * Note that decision making process defined in this document manages who is
  listed as a contributor to the BIDS community.
  * For more details on recognizing contributions please review the
  [contributing guidelines](CONTRIBUTING.md/#recognizing-contributions).

* **Core Contributor**: anyone who has made a major contribution to the BIDS
community and has a good understanding of the specification as a whole.
  * A Core Contributor is by definition a Contributor.
  * *NOTE: This definition is a work in progress.*

* **Maintainer**: a Core Contributor who has committed to 6 months of support
for the long term development of the specification at the time that a pull
request is opened.
  * A Maintainer is by definition a Core Contributor.
  * *NOTE: This definition is a work in progress.*

<!-- TO DO: Add definitions of:
  * Review
  * Approve
  * Request changes
  * Dismiss
  * Vote
-->

## Principles

This section explains some of the principles that drive the process for making
decisions within the BIDS community.

* [All decisions are made via pull request](#all-decisions-are-made-via-pull-request)
* [Anyone can open a pull request, any contributor can review](#anyone-can-open-a-pull-request,-any-contributor-can-review)
* [Reviews are stratified according to their impact on the internal consistency of the specification](#reviews-are-stratified-according-to-their-impact-on-the-internal-consistency-of-the-specification)
* [Governance changes are always classed high impact](#governance-changes-are-always-classed-high-impact)
* [Releases are always classed high impact](#releases-are-always-classed-high-impact)
* [One of three review options are available: Comment, Approve or Request changes](#one-of-three-review-options-are-available-comment-approve-or-request-changes)
* [Approvals are dismissed when any update is made](#approvals-are-dismissed-when-any-update-is-made)
* [Request changes reviews are dismissed if the review has not been updated 2 weeks after new commits are made](#request-changes-reviews-are-dismissed-if-the-review-has-not-been-updated-2-weeks-after-new-commits-are-made)

#### All decisions are made via pull request

Every modification of the specification (including a correction of a typo,
adding a new Contributor, an extension adding support for a new data type, or
others) or proposal to release a new version needs to be done via a pull
request (PR) to the Repository.

#### Anyone can open a pull request, any contributor can review

Anyone can open a pull request to propose a change. This action is not limited
to Contributors.

Any Contributor can review a pull request.

In fact, the success of the BIDS project ***depends on as many people as
possible*** opening pull requests and giving feedback on others' suggestions.

#### Reviews are stratified according to their impact on the internal consistency of the specification

When a pull request is opened it must be stratified into *low*, *medium* or
*high* impact on the internal consistency of the specification. This action
should be undertaken by the person who has opened the pull request although
Contributors may recommend changes to the rating in their reviews.

The motivation for this requirement is to give members of the BIDS community
some guidance on how much time to allocate to ensuring that the changes are not
introducing potential future conflicts to the specification. The review
requirements - described below - are different for the different impact tiers.

Some examples to help guide the classification:
  * A low impact change: fix a typo, add an example, update formatting
  * A medium impact change: changing/clarifying the description of a metadata field
  * A high impact change: merging a BIDS extension, adding a new metadata field

#### Governance changes are always classed high impact

While they do not affect the internal consistency of the specification,
governance changes are always classed as high impact changes due to the
potential effects on the membership and coordination of the BIDS community.

#### Releases are always classed high impact

Decisions to release a new version of the BIDS specification are always
classed as high impact changes as they affect the rules that the broader
neuroimaing community follows when they put their data in BIDS format.

#### One of three review options are available: Comment, Approve or Request changes

A Contributor may leave a review with one of
[three status options](https://help.github.com/articles/about-pull-request-reviews/#about-pull-request-reviews):

* **Comment**: Submit feedback without explicitly approving the changes or
  requesting additional changes.

* **Approve**: Submit feedback and approve merging the changes proposed in the
  pull request.

* **Request changes**: Submit feedback that must be addressed before the pull
  request can be merged.

  Note that any review that requests changes must also include an explanation of
  what changes should be made and a justification of their importance.

If a Contributor needs more time to review the pull request, they may use the
*Request changes* status to ask for more time to review a PR.

Contributors are encouraged to **keep their reviews up to date** as new commits
are made to the PR. For example, once requested changes are made to the
reviewer's satisfaction, the reviewing Contributor should change their status to
*Approve*.

#### Approvals are dismissed when any update is made

All approval reviews are dismissed after updates are made to the pull request.
This is equivalent to
[stale review dismissal](https://help.github.com/articles/enabling-required-reviews-for-pull-requests/)
on GitHub and is in place to ensure that the reviewers have approved the most
recent version of the PR.

#### Request changes reviews are dismissed if the review has not been updated 2 weeks after new commits are made

When a Request changes review is added it must be updated by the same
Contributor who left it. This can cause the development process to stall if
that reviewer is not responsive to new updates to the PR.

Although it would be preferable for the original reviewer to continue to engage
with the person who opened the pull request, their Request changes review can
be dismissed 14 days after new commits addressing the review have been added.

## Merge requirements

### Low impact

A **low impact** PR is eligible to be merged if the following conditions are
met:

1. The last commit is at least 5 working days old to allow the community to
   evaluate it.
1. The PR features at least two [Reviews that Approve](https://help.github.com/articles/about-pull-request-reviews/#about-pull-request-reviews)
   the PR from Contributors who are not authors of the PR.
1. The PR does not feature any [Reviews that Request changes](https://help.github.com/articles/about-required-reviews-for-pull-requests/).
1. Does not feature "WIP" in the title (Work in Progress).
1. Passes all automated tests.

All Contributors to the BIDS specification are expected to work to build
consensus around all decisions. That will often mean accepting that done is
better than perfect, especially for updates that have low impact on the internal
consistency of the specification.

If consensus can not be reached for a low impact PR, it can be merged if two
Core Contributors Approve the pull request. When they agree, the Core
Contributors can ask a Maintainer to dismiss any Reviews that Request changes so
that the requirements for merging detailed above can be met.

### Medium impact

A **medium impact** PR is eligible to be merged if the requirements for a low
impact PR are met along with the following requirement:

1. The PR features at least two additional [Reviews that Approve](https://help.github.com/articles/about-pull-request-reviews/#about-pull-request-reviews)
   the PR from Core Contributors.

Note that this requires a four reviews in total. Two reviews must be from Core
Contributors and two can be from any Contributor.

All Contributors to the BIDS specification are expected to work to build
consensus around all decisions. That may mean living with some inconsistencies
or imperfections to permit the growth and development of the specification.

If consensus can not be reached for a medium impact PR, it can be merged if two
Maintainers Approve the pull request. When they agree, a Maintainer can dismiss
any Reviews that Request changes so that the requirements for merging detailed
above can be met.

### High impact

A **high impact** PR is eligible to be merge if and only if the requirements of
a medium impact PR are met along with the following requirements:

1. The PR features at least two additional [Reviews that Approve](https://help.github.com/articles/about-pull-request-reviews/#about-pull-request-reviews)
   the PR from Maintainers.

Note that this requires six reviews in total. Two reviews must be from
Maintainers, two must be from Core Contributors and two can be from any
Contributor.

All Contributors to the BIDS specification are expected to work to build
consensus around all decisions. For high impact decisions this is likely to
require ongoing discussions with a broad representation from the BIDS community.

If consensus can not be reached for a high impact PR, the community will be
asked to vote on the proposal.

## Process for a vote on high impact pull requests

If the author of a PR that has been classified as having a high impact on the
internal consistency of the BIDS specification, or a high impact on the
governance and management of the community, the community can be asked to vote
on the decision.

The wording of a BIDS community Vote is always the same:
> Please select one option for pull request #XX
> - [ ] Approve the pull request
> - [ ] Close the pull request without merging
> - [ ] No opinion

The third option ("No opinion") is included to monitor the number of people
voting across the BIDS community. Members are encouraged to review the pull
request independently, but to choose "No opinion" if they are not qualified to
make a decision based on the content of the update.

A Vote freezes the PR. Contributors are asked not to comment on nor submit new
commits to the PR while a vote is ongoing. If a comment or commit is
accidentally made  during that period it should be deleted or reverted as
appropriate.

The following rules apply to all Votes:

1. A Vote can only be triggered by a Maintainer.
1. A Vote can only be triggered after the six required reviewers have agreed
that consensus can not be met on the decision.
1. A Vote should open 5 working days after the decision that consensus can not be
reached to permit a "cooling off" period from what is likely to have been a
difficult collaborative discussion.
1. A Vote must be announced on the BIDS mailing list.
1. A Vote is open for 5 working days.
1. If a Vote on a different pull request has closed within 15 working days of
the opening date for the new Vote, the start date must be postponed until 15
days have elapsed.
1. The outcome of the vote is decided based on a simple majority excluding the
"No opinion" responses.

Note that a Vote when consensus can not be reached relies on an honour system
that members of the BIDS community will not vote more than once.


## Additional notes

There are no restrictions on how the content of the PR is prepared. For
example it is perfectly fine for a PR to consist of content developed by a
group of experts over an extended period of time via in person meetings and
online collaborations using a Google Document.

To facilitate the triaging of incoming PR you can subscribe to notifications for
new PRs proposing changes to specific files. To do this add your Github name
next to the file you want to subscribe to in the [CODEOWNERS](CODEOWNERS)
file. You will automatically be ask to review each relevant PR that updates the
file you have put your name next to.

Note that lack of your review will not prevent the PR from being merged so if
you think the PR needs your attention, please review it promptly or request more
time via Request changes as [described above](#review-options).