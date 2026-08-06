# AGENTS.md — scoop-deectx

Reference for coding agents (Claude Code, GitHub Copilot, opencode) working in this repo.

## What this is

The **Scoop bucket** for [deectx](https://github.com/deectxone/deectx). Users run
`scoop bucket add deectx https://github.com/deectxone/scoop-deectx && scoop install deectx`;
Scoop reads the manifest from this bucket's root-level `bucket/` folder.

This is a **single-manifest repo** — there is no application code here.

| Path | Responsibility |
|------|----------------|
| `bucket/deectx.json` | The Scoop manifest (version, x86_64-pc-windows-msvc URL + hash, autoupdate/checkver) |
| `README.md` | Bucket usage |

## How to make a change

- **Do not hand-edit `bucket/deectx.json` for a release.** It is regenerated and pushed here
  automatically by the `release` workflow in the upstream
  [deectx](https://github.com/deectxone/deectx) repo on every tag (via the `SCOOP_BUCKET_TOKEN`
  secret) — the version, download URL, and sha256 are recomputed to match the Windows release zip.
  Manual edits get overwritten on the next release.
- Structural manifest changes (new architectures, bin names, checkver/autoupdate logic) belong
  upstream in `deectx/install/scoop/deectx.json`, which is the source the workflow copies here.

## Note on automation

There is **no `agents-doc-freshness` CI check here** — the only file that changes is the
bot-updated manifest, so a source-vs-doc drift check would fire on every release and only produce
noise. Keep this file accurate by hand if the manifest's shape or the sync mechanism changes.

Upstream / source of truth: https://github.com/deectxone/deectx
(manifest generator: `deectx/install/scoop/deectx.json` + `deectx/.github/workflows/release.yml`)
