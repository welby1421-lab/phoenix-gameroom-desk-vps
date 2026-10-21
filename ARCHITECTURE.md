# ARCHITECTURE.md — phoenix-gameroom-desk-vps

## What this is
Placeholder repo. The README describes a planned "Phoenix Gameroom Agent Desk Phase 2 — VPS deploy (Dockerfile, compose, DEPLOY.md)", but no app code, Dockerfile, compose file, or DEPLOY.md has ever been committed. Nothing deploys from this repo; nothing runs from it.

## Where the live code is
Phoenix Game Room / Gameroom360 code lives in the **altiras360** org, not here:
- `altiras360/phoenix-gameroom-app` — main Next.js app.
- `altiras360/phoenix-agent-desk`, `altiras360/phoenix-player-portal`, `altiras360/phoenix-gameroom-ledger` — live VPS mirrors (secrets on server only).
- `altiras360/phoenix-gameroom-vps-clone` — snapshot copy of live VPS code.
- `altiras360/gameroom360-control` — VFAi Genesis control site.
- `altiras360/transaction-ticker` — hourly ticker, read-only analytics.

The `welby1421-lab/phoenix-*` repos (including this one, `-desk`, `-desk-phase2`, `-gameroom-agent-desk`, `game-room`, `phx-mig-*`, `phoenix-transaction-ticker`, and assorted push/access/tmp probes) are placeholders or scratch — do not build in them.

## Do not break
- Do not commit app code, Dockerfiles, secrets, or VPS credentials here. Build in the altiras360 org repos above.
- Never name anything "North Star"/"Northstar"; use "Key West".
- Never commit secrets; document env var NAMES only.
- Any outbound SMS/email/call in the real app must check the shared DNC hub (`welby1421-lab/ecosystem-dnc`, env `DNC_HUB_URL`/`DNC_HUB_TOKEN`) and fail closed; opt-outs must /add to it.

## Keep this file current
Any PR that changes what this repo is or what lives here must update ARCHITECTURE.md in the same PR.
