# Project

## Open Questions
- Sepo 0.5.0 update (PR #18, open draft) is blocked: 0.5.0's discussion.ts createDiscussion returns only {url}, breaking target-owned .agent/src/cli/publish-literature-update.ts which reads discussion.id. Needs a target-side fix (explicit GraphQL node-id lookup) before the update can merge.
- Auto-diary emits entries on no-activity days (08-05/07/08/09 all thin/silent), contradicting content/diary/index.md:9 'Days when nothing notable happened get no entry.' Defensible as a silence-theme arc but a maintainer-judgment call — worth flagging on future thin-day diary reviews.
