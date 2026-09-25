# Axiom Relay Pilot

Public, transport-only mailbox used for a narrow Axiom connectivity pilot.

## Security boundary

This repository is **not an authority source**. Axiom must reject any message here unless it independently passes all local checks, including:

- Ed25519 signature verification against a locally pinned trust anchor;
- request expiry and persistent replay protection;
- exact caller/action/resource allowlisting;
- local gateway permission policy and an explicitly registered handler.

## Public-data rule

Assume every byte committed here is permanently public.

Allowed during this pilot:
- harmless, non-sensitive control/read messages such as an Open WebUI health check.

Never publish here:
- passwords, tokens, API keys, private keys, authentication material;
- personal information, conversation content, files, or private prompts;
- machine secrets, private network details, or sensitive operational data;
- commands carrying write, delete, execute, or mutation authority.

## Purpose

The pilot lets a local Axiom connector poll outbound over ordinary HTTPS without storing a GitHub credential or unlocking an SSH key. The public repository only transports signed envelopes; the local Axiom gateway remains the enforcement point.

This is a transition mechanism, not the final production relay.
