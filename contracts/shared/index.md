# Shared capability catalog

Revision: catalog-r3, reconciled three-target draft. Document agreement: Draft. Implementation evidence: Untested. Existing output directory was absent at start; no old catalog or private source was consulted. Entries follow responsibility discovery during nginx, then profile review for redis and sshd. This file is navigation, not a second normative definition.

The canonical future maintained source home is shared/; no source directory or implementation is created in this documentation run. Each proposed entry will identify its one source home, owner, prerequisites, exact revision, consumer profiles and acceptance identifiers. No component pass or binary qualification exists.

| Capability and revision | Purpose / responsible owner / future source home | Consumer profiles | Prerequisites / acceptance | Status |
| --- | --- | --- | --- | --- |
| [bounded-stream](bounded-stream/bounded-stream.md), stream-r2 | Exact bounded byte delivery; shared transport maintainer; shared/bounded-stream/ | nginx WEB/ORIGIN; Redis; SSH. Service-specific profiles explicitly include framing and cumulative costs. | Approved baseline; AS-STREAM-01 through 06 | Draft / Untested; no implementation |
| [cryptography](cryptography/cryptography.md), crypto-r3 | Standard owned cryptographic results; shared crypto maintainer; shared/cryptography/ | TLS algorithms for nginx/Redis; SSH modern plus mandatory-implementation algorithms under CRYPTO-SSH IDs | Approved baseline and OS entropy; AS-CRYPTO-01 through 05 and AS-CRYPTO-SSH-01/02/03 | Draft / Untested; no implementation |
| [tls](tls/tls.md), tls-r3; [research](tls/research.md) | Authenticated TLS byte transport; shared TLS maintainer; shared/tls/ | nginx W13 TLS1.3-only; Redis R13 TLS1.3 and additive R12 TLS1.2. SSH has no TLS dependency. | crypto-r3 TLS and stream-r2; AS-TLS-01 through 06, AS-TLS-12-01 through 03 | Draft / Untested; no implementation |

Dependency direction: nginx and Redis to TLS/stream; TLS to crypto/stream; SSH to crypto/stream; crypto/stream to baseline. No cycle or hidden dependency on another target. Exact target pins resolve to the rows above. No agreed consumers or prior agreed canonical revision exist. During this run r1 web discovery was extended to r2 for Redis TLS1.2/SSH crypto; earlier required TLS1.3 web behavior/defaults were checked and retained. Stream's provisional generic maximum was challenged and reconciled into named consumer profiles before freeze, so no nonexistent agreed maximum was overwritten.

## Consumer impact and replay map

| Proposed change | Direct and indirect consumers | Profile preservation / future replay |
| --- | --- | --- |
| Common STREAM-01 through 06 | Direct nginx client/origin, Redis and SSH; indirect TLS and all its consumers | Exact bytes, unread delivery, cancellation, bounds, deadline, reload and provenance scenarios for every role, then each target's functional/resource/performance/fuzz gates. No imported bans or application authority. |
| Common CRYPTO-01 through 05 | Direct TLS and SSH; indirect nginx and Redis | Relevant standard vectors/independent oracles, malformed/entropy/timing/lifetime/compiler checks and each affected transport/service integration; common ancestry counted once. |
| CRYPTO-SSH additions | Direct SSH; TLS affected only if common source/promises change | No new TLS default/algorithm requirement silently imposed. SSH KEX/signature/record/rekey and application/resource/efficiency/fuzz replays; impact review determines other source paths. |
| TLS common plus R12 addition | Direct nginx W13 and Redis R12/R13; SSH excluded | W13 must continue rejecting TLS1.2. Both Redis versions interoperate and retain AUTH authority; all affected identity, cancellation, limits, resource, efficiency and final fuzz rows replay. |

Single owner coordinates each proposed extension against its current draft identity. An agreed revision in a future run stays canonical while a proposal negotiates; current run has no actual prior agreement to supersede. Component agreement/availability/test results remain separate from every consumer's evidence.

SSH dependency reconciliation: the earlier mandatory implementation gap is now integrated into crypto-r3 as SSH-only CRYPTO-SSH-03, with modern negotiation still disabled for legacy algorithms under RFC4251. All target/shared current pins resolve to crypto-r3; TLS consumers select only its TLS profile. The earlier proposal is [retained rationale](../sshd/research.md#mandatory-implementation-rationale), not an approved or separate canonical crypto contract. New primitive/provenance/vector/denial/timing obligations and 56-hour SSH component budget remain Draft/Untested. This resolves the omitted responsibility in the documents, not implementation coverage or user policy adoption.

Final certificate-profile review explicitly maps current PKI/TLS1.2 updates and safe critical-policy/noRevAvail/unsigned/path constraints under TLS-03/05/06 and TLS-12-01/02. Both nginx W13 and Redis R12/R13 retain valid-neighbor and refusal integration scenarios; SSH acquires none. These are unaccepted draft profile details, with no component/runtime pass or expanded provider allowance.

## Current r2 consumer planning impact

crypto-r3 is reused unchanged. stream-r2 clarifies continuing canceled-delivery ownership/accounting with stable IDs; tls-r3 is a dependency-only revision binding it, with unchanged wire/default/security promises. catalog-r3 coordinates these current revisions. Target contracts advance to nginx-r2, redis-r2, sshd-r2; Redis command catalog remains redis-catalog-r2. SSH cleanup change is target-owned: stream cancellation does not promise arbitrary account-workload death, grant slot or kernel progress. Continued attributable delivery charges remain STREAM-02/03; SSH owns descendant authority/pending accounting. Other targets acquire no login policy, job limits or new authority.

All three consumers now use qualification-r2 and their revised acceptance/task sections for independent statistics, legal cycles and finite budgets. Shared component prerequisites152hremain separate, not a pass or a second maintained source. Future change to common source/promises still triggers all direct/indirect integration/resource/performance/final-fuzz replays. No current component source, binary or runtime result exists.

The stream-r2common cleanup clarification affects every direct/indirect consumer; NGX-10/12, R-06/08/12, S-07/12and their scenarios/tasks require pending-charge/cadence/reclamation integration. No generic delivery profile gains authority to terminate SSH account workloads; that remains S-OS-01/S-07.

crypto-r3is unchanged in every normative requirement/profile. Its current document hash differs from the archived copy only for relocated rationale navigation and current consumer metadata;those editorial changes are explicitly included in the new package identity. This is no claim that two different byte sequences share an exact artifact hash,or that any old evidence transfers.
