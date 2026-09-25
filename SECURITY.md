# Security Notes

This repository intentionally contains no Axiom source code, credentials, private keys, personal data, or sensitive prompts.

A valid-looking relay envelope is not trusted merely because it appears in this repository. Local Axiom must independently verify its detached Ed25519 signature, freshness, replay status, exact allowed action/resource pair, and local permission policy before handling it.

If you discover a secret or personal data committed here, treat it as exposed and rotate/remove it from the originating system. Git history should be assumed permanent.
