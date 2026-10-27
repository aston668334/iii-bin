# iii-bin

Unmodified Linux and Windows release binaries mirrored from [iii-hq/iii](https://github.com/iii-hq/iii/releases).
This is **not** the official distribution; use the upstream repository for support and the latest source.

- Releases: see the [Releases](https://github.com/aston668334/iii-bin/releases) page. Each release carries a `SHA256SUMS` file.
- Licenses (copied from upstream, unchanged): the engine runtime is under the
  [Elastic License 2.0](LICENSE-ELv2.txt); the console is under [Apache-2.0](LICENSE-Apache-2.0.txt).
  See the upstream README for the full licensing table.

## Layout

The binaries live in [`bin/`](bin/) (currently **v0.22.1**, see `bin/VERSION`), unmodified and still packed as the
upstream `.tar.gz` (Linux) or `.zip` (Windows). Older versions are available from git history and the Releases page.
v0.11.2 (Linux and Windows) is kept in [`bin/v0.11.2/`](bin/v0.11.2/) with its own `SHA256SUMS`.

```bash
# verify, then unpack the build you need
cd bin && sha256sum -c SHA256SUMS --ignore-missing
tar -xzf iii-x86_64-unknown-linux-gnu.tar.gz
```

Windows builds (`*-pc-windows-msvc.zip`) exist for `x86_64`, `aarch64` and `i686` (`iii` and `iii-console` only; upstream ships no Windows worker/init/libkrunfw).
On PowerShell: `Get-FileHash iii-x86_64-pc-windows-msvc.zip` then `Expand-Archive iii-x86_64-pc-windows-msvc.zip`.

Pick `*-gnu` for glibc distros, `*-musl` for static/Alpine, and `aarch64` / `armv7` for ARM.
