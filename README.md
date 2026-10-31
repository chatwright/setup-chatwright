# setup-chatwright

Install an exact [Chatwright CLI](https://github.com/chatwright/cli) release in GitHub Actions without Go. This action installs the CLI only; workflows choose which commands to run. Release-provided license and notice files are kept alongside the executable.

`version` is required and must be an exact release tag. `expected-sha256` optionally supplies an independently obtained digest for the selected archive. A checksum from the same release detects corruption but cannot authenticate a replaced release. Outputs include the installed tag and binary path.

The action supports Linux, macOS, and Windows on amd64 and arm64 where the requested release publishes those assets.

```yaml
- uses: chatwright/setup-chatwright@b8f13d288b698c09ac31b763109b4ec21149c573
  with:
    version: v0.10.2
- run: chatwright --version
```

Self-hosted runners need PowerShell (`pwsh`); Unix runners also need `tar` and `chmod`.
