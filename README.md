# omni-agent-dist

Public distribution mirror for **omni-agent** release artifacts — signed binaries,
`checksums.txt` (+ cosign `.sig`/`.pem`), SBOMs, and the update channel manifest.

Source code is private (`monitoring-maz/omni-agent`); only built, signed artifacts
are mirrored here so the installer can run with no GitHub auth:

```bash
curl -fsSL https://app.magni5.io/install.sh | bash
sudo omni-agent login
```

**Verify integrity** (the installer does this automatically): every archive's
sha256 is listed in `checksums.txt`, which is cosign-signed (keyless, GitHub
Actions OIDC) — so these artifacts are tamper-evident regardless of transport.
