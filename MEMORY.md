# Memory

## Durable
- Auto-diary autonomy is fully gated: the orchestrator chain self-approves/self-merges only when AGENT_ALLOW_SELF_APPROVE and AGENT_ALLOW_SELF_MERGE are both set (default false); otherwise it stops at agent review.
- Two auto-diary PRs for the same day collide: whichever merges first owns content/diary/YYYY-MM-DD.md, the other goes merge-DIRTY. Recover a failed run by appending-within-day, not by opening a competing full-day PR.
