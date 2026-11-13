# Adopted practical v1 scope

Adopted 2026-11-07. This is the reduced delivery scope for a practical v1 of the three services. The original contracts remain a broader, historically preserved draft. Publishing these requirements does not assert that an implementation or deployment has passed them.

| Service | Practical v1 behavior |
| --- | --- |
| Redis | Commands required by the current application, authentication, TLS, TTLs, transactions including WATCH behavior, and one documented persistence mode with ordinary restart recovery. |
| nginx | Static files, fixed-origin reverse proxy, HTTP and HTTPS, basic authority/prefix routing, and finite request limits. |
| SSHD | Password and public-key login for the selected account, interactive shell and PTY, remote commands with correct streams and status, disconnect and useful reconnect. Apply the [adopted SSH lifecycle](coordination/amendments/ssh-openssh-lifecycle-r1/amendment.md). |

Delivery includes a reproducible fresh isolated installation, usable configuration and protected logs, focused negative and recovery checks, and integrated acceptance on identified artifacts. Supported persistent data must survive an ordinary restart under the documented guarantee. An unexecuted, skipped, or failed check is never a pass.

The essential acceptance journeys are: valid and invalid SSH password/key login, exact command streams/status, PTY input/resize and reconnect; Redis application workflows over authenticated TLS, expiry, WATCH conflict handling and restart recovery; nginx static delivery, safe paths, routing and HTTP/HTTPS proxying including bounded upstream failure; and ordinary-client TLS trust and invalid-certificate rejection. Authentication, intended account permissions, secret protection, bounded service-owned state, correct supported data, and honest errors remain required.

Clustering, replication, broad server/configuration compatibility, advanced HTTP, SSH forwarding and file-transfer subsystems, comparative performance targets, and exhaustive qualification, fuzz and resource campaigns are deferred from this v1 release gate. Deferral does not mark the original full specification complete. Known preauthentication isolation limitations must be reported accurately. This scope does not assert a production Internet rollout or grant host/account changes.

The original full-spec [service contracts](contracts/README.md) are useful as requirements and future work; their proposed product choices and acceptance matrices do not by themselves prove adoption or passing runtime evidence.
