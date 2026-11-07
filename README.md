# Tach release key

Tach self-host packages are signed with this [minisign](https://jedisct1.github.io/minisign/) public key. Its key ID is `3ED2D71C174A84F7`. It was established on 28 October 2026.

```text
untrusted comment: minisign public key 3ED2D71C174A84F7
RWT3hEoXHNfSPouklRIs0r5zm+gbI7wA0/2esk8C164WwFi7bPqDhEeo
```

This repository is one of two independent places the key is published. The other is the Tach documentation site. The install guide shows how to compare the two copies before verifying a package. If they differ by even one character, do not install, and email hello@r90group.com.

Private prereleases up to and including 0.2.5 used key ID `4FF01EA23537AE88`. Verify those packages with their original key.

## Agent release key

The Tach computer agent has its own Ed25519 public key, in [agent-release.pub](agent-release.pub). That file holds one base64 line encoding the 32 raw public-key bytes; it is not a minisign key. Its SHA-256 key ID is `555eba5daf4be38772bdb93db165fad7ec034299ce77ea00043735ad2cdd0418`, with security floor 1.

The versioned installers, `https://tach-site.pages.dev/tools/tach/releases/vVERSION/agent/install.sh` and `install.ps1`, embed this key. They use it to authenticate the manifests and binaries they download from your instance, and never take their trust root from that instance.

For IT distribution:
1. Verify the matching version's `agent/SHA256SUMS` against `agent/SHA256SUMS.minisig` using the package release key in `trusted-release.pub` in this repository.
2. Compare the `agent-install.sh` or `agent-install.ps1` SHA-256 entry with the installer you downloaded.
3. Distribute the authenticated digest through your own independent IT channel.

The package release key and this agent key have different purposes.
