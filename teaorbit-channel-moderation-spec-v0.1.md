# teaorbit channel moderation spec v0.1

## 

Quick summary: Channels will be moderated via "rules" that trigger moderation actions \(ban, silence etc.\) where the rules are voted in by the community that is active in the channel. This document highlights how the rules are voted and implemented.

### 

### Community tuning parameters

Every rule will have the same inputs, which is a list of "tuning parameters" which are provided by the core codebase. Examples include:

* User account age on site since signup
* User membership age in the specific channel
* KYC \(anonymous, botness/humanness, email, phone and other third party logins & verifications\)
* User activity in channel \(messages, votes, flags\)
* Feedback on user by other users \(replies, votes, flags\)
* Past moderator actions taken in specific channel or on site in general
* Various reputation and Hostility scores \(per site & per channel\)

These numeric or boolean parameters will be passed into the moderation algorithms.

### 

### Moderation algorithms

There will be a database of available moderation algorithms that use the tuning parameters as inputs, and output boolean values for different website actions, such as "Can post message", "can vote, "can flag", "can vote on rules", "can delete posts" so on so forth.

Each moderation algorithm will choose One action, One algorithm, and a set of constants \(multipliers\) and boolean operators \(and, or\) that operate on any combination of the available tuning parameters

### 

### Rule selection

Upon the creation of a channel, the channel creator \(being the only member\) will have full power over choosing the active rule sets \(i.e. moderation algorithms\) and the associated parameter tuning.

As the channel matures, members who are active on the channel will gradually gain more voting power over changing active rules or their parameter multipliers.

### 

### Voting on rules

Each user that qualifies as a channel member will be able to propose rule changes to the channel. A proposal will initiate a vote which will have the power to change existing rules.

For example, a user can propose to change the voting threshold to 60% such that 60% consensus is needed among members to pass a new rule.

Then, another user can propose to close the channel down to anonymous users -- i.e. only allow posting by users who have provided some sort of KYC. If this proposal gets 60% support it gets implemented as an active rule.

Rules build up over time. A channel may choose to introduce "rule expiries" to automatically revoke rules that do not get re-voted in.

