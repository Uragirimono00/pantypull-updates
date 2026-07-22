# PantyPull — update host

Hosts the in-editor auto-update manifest and the encrypted release packages for
**Uragirimono PantyPull**.

- `pantypull_version.json` — the manifest the tool checks (`{version, url, notes}`).
- `PantyPull_vX.Y.Z.unitypackage.enc` — the AES-encrypted release package the tool
  downloads and decrypts on **Update now**.

Only the tool (with its embedded key) can decrypt the `.enc`; the URL alone is useless.

## Releasing an update
1. In Unity: bump the `Version` const, then **Uragirimono ▸ PantyPull ▸ Export Release Package…**
2. **Uragirimono ▸ PantyPull ▸ Encrypt Package for Release…** → produces the `.enc`
3. Copy the `.enc` here, update `pantypull_version.json` (same version + point `url` at it)
4. `git add . && git commit -m "vX.Y.Z" && git push`
