# scoop-deectx

Scoop bucket for [deectx](https://github.com/deectxone/deectx) — a local-first
PII-masking reverse proxy for AI coding tools.

## Install

```powershell
scoop bucket add deectx https://github.com/deectxone/scoop-deectx
scoop install deectx
```

## Update

```powershell
scoop update deectx
```

## Manifest

`bucket/deectx.json` is refreshed automatically by the `release` workflow in
the main [deectx](https://github.com/deectxone/deectx) repo whenever a new
version is tagged — the hash and download URL are regenerated to match the
`x86_64-pc-windows-msvc` release artifact. Do not edit it by hand; changes
will be overwritten on the next release.
