# Memory

## Durable
- Auto-diary autonomy is fully gated: the orchestrator chain self-approves/self-merges only when AGENT_ALLOW_SELF_APPROVE and AGENT_ALLOW_SELF_MERGE are both set (default false); otherwise it stops at agent review.
- Two auto-diary PRs for the same day collide: whichever merges first owns content/diary/YYYY-MM-DD.md, the other goes merge-DIRTY. Recover a failed run by appending-within-day, not by opening a competing full-day PR.
- Repo visibility snapshots (preview-registry isPrivate, R2 META visibility) are written server-side by preview-api at canonical-deploy time; this repo's only lever is agent-deploy-site-main.yml posting canonical:true to /api/deploy/preview. See [[github/self-evolving/diary/issue-10.json]].
- Grouped Dependabot bumps recur and are not auto-merged: big production-dependencies groups with major jumps pass CI but risk 'renders, but wrong', so they're closed unmerged; Dependabot re-raises the same group (e.g. 30→31 updates). See [[github/self-evolving/diary/pull-13.json]].
- Diary caution-count keeps getting miscounted (fixed 41f6cfa, faa0d48): count times the caution was actually written, not repo-appearances; a declined/relitigation-refused entry does not increment.
- Diary reviews: check novelty claims ('first-time', 'not logged yet', 'now downstream') against prior entries — recurring miss: 08-01/#19 reframed hcllms/#1/#15 (logged 07-20,07-24) as new; 08-03/#21 called digital-garden-template 'a leaf I hadn't logged yet' (logged 07-27).
- _meta.json ordering differs by folder: diary = newest-first (prepend), ideas = oldest-first (append-to-end, ascending planted date). SKILL.md scopes 'newest first' to the diary only.
- When sourcing self-evolving/repo orchestration threads, don't read parent_round/stale state:failed bodies as attempt counts: a child task's implement can succeed and produce a PR directly, with the only failure being a later transient fix-pr run. Verify sequence against the PR body ('Closes #N'). See 08-03/#21.
