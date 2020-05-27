# Technical details - moderation

Boolean checks:

\(user type / spiel\) user can read, write, edit, delete 

\(user type / user\) user can punish, ban, silence, label

\(user type / channel\) user can edit, manage, create sub-channels etc, request access



votes: \(user / spiel\) and \(user / user\) and \(user / channel\)



rules: proposed, active, expired



user type properties: title, shortname, description

user properties: past punishments, role, status, reputation, \# posts, \# likes, \# bookmarks etc

spiel properties: score, likes, flags, reactions

channel properties: visible globally, spiels public/private, reaction types, description, available plugins, search shortcuts \(show all active rules, today's top posts, etc\)



if user has at least 30 posts over 2 weeks without any punishments, they are a member

if user has 3 punishments over 4 weeks, they are banned forever

if spiel has flags by 50% of members, delete

if spiel has flags by 2+ moderators, delete

if spiel has 3+ "funny", tag it into \#channel/funny

if rule is active, it cannot be edited



lists & aggregate functions

"context" on actions??? context having all available metrics to program



