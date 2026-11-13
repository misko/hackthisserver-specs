# Three-service specification archive

This repository publishes the Markdown recipe and requirements for an independently authored nginx-like HTTP server, Redis-like data service, and SSH server. The documents describe intended behavior, research, security considerations, and acceptance checks. They are **requirements and proposed checks**, not proof that any current deployment or binary satisfies them.

The source snapshot is revision `3380672406a557e8ff67518fda0a8c502fa7baef`, selected on 2026-11-13. The 21 files under `recipe.md` and the service/shared contract directories are copied from that revision. This public README, [adopted scope](ADOPTED-SCOPE.md), [decision note](contracts/decisions.md), and the [SSH lifecycle excerpt](coordination/amendments/ssh-openssh-lifecycle-r1/amendment.md) explain how to read the historical drafts. Unpublished historical archives, coordination records, source code, and test evidence are intentionally outside this set. Links within the selected Markdown set resolve here; references to prior private history are historical context, not public dependencies.

Start with the [recipe](recipe.md), which describes the specification and evaluation process, then read the [adopted practical v1 scope](ADOPTED-SCOPE.md). The full contracts below preserve a wider draft target. Where the v1 scope or SSH lifecycle amendment differs, the adopted document governs that release scope. Deferred full-spec requirements remain recorded for future work.

| Area | Behavior | Research | Acceptance | Security |
| --- | --- | --- | --- | --- |
| nginx | [Contract](contracts/nginx/nginx.md) | [Research](contracts/nginx/research.md) | [Acceptance](contracts/nginx/acceptance.md) | [Security review](contracts/nginx/security.md) |
| Redis | [Contract](contracts/redis/redis.md) and [command catalog](contracts/redis/catalog.md) | [Research](contracts/redis/research.md) | [Acceptance](contracts/redis/acceptance.md) | [Security review](contracts/redis/security.md) |
| SSHD | [Contract](contracts/sshd/sshd.md) | [Research](contracts/sshd/research.md) | [Acceptance](contracts/sshd/acceptance.md) | [Security review](contracts/sshd/security.md) |

Shared requirements: [index](contracts/shared/index.md), [TLS](contracts/shared/tls/tls.md), [TLS research](contracts/shared/tls/research.md), [cryptography](contracts/shared/cryptography/cryptography.md), [bounded streams](contracts/shared/bounded-stream/bounded-stream.md), [common qualification](contracts/qualification.md), and [related research](contracts/related-research.md).

The existing [AGENTS.md](AGENTS.md) is an earlier, standalone minimal-SSH acceptance contract retained for historical compatibility. Its public-key-only profile and some cleanup promises differ from the later three-service practical v1 scope, which includes SSH password login and the adopted OpenSSH-style lifecycle. Read it as that earlier profile, not as evidence of the later implementation or a replacement for the adopted scope.
