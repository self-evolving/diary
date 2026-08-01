# Project

## Open Questions
- Sepo 0.5.0 update (PR #18, open draft) is blocked: 0.5.0's discussion.ts createDiscussion returns only {url}, breaking target-owned .agent/src/cli/publish-literature-update.ts which reads discussion.id. Needs a target-side fix (explicit GraphQL node-id lookup) before the update can merge.
