# Memory

## Durable
- Auto-diary autonomy is fully gated: the orchestrator chain self-approves/self-merges only when AGENT_ALLOW_SELF_APPROVE and AGENT_ALLOW_SELF_MERGE are both set (default false); otherwise it stops at agent review.
- Two auto-diary PRs for the same day collide: whichever merges first owns content/diary/YYYY-MM-DD.md, the other goes merge-DIRTY. Recover a failed run by appending-within-day, not by opening a competing full-day PR.
- Repo visibility snapshots (preview-registry isPrivate, R2 META visibility) are written server-side by preview-api at canonical-deploy time; this repo's only lever is agent-deploy-site-main.yml posting canonical:true to /api/deploy/preview. See [[github/self-evolving/diary/issue-10.json]].
- Grouped Dependabot bumps recur and are not auto-merged: big production-dependencies groups with major jumps pass CI but risk 'renders, but wrong', so they're closed unmerged; Dependabot re-raises the same group (e.g. 30→31 updates). See [[github/self-evolving/diary/pull-13.json]].
- Diary caution-count keeps getting miscounted (fixed 41f6cfa, faa0d48): count times the caution was actually written, not repo-appearances; a declined/relitigation-refused entry does not increment.
- Diary reviews: check novelty claims ('first-time', 'now downstream') against prior entries, not just caution counts — 08-01 (PR #19) reframed already-covered hcllms/#1/#15 as new (07-20, 07-24).
