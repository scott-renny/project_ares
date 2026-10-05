# VM Catalog

Ares uses an **on-demand catalog**, not a permanently running VM inventory.

| ID | Purpose | Persistence | When to use |
|---|---|---|---|
| ATTACK-01 | Kali operator tooling | Reusable clean template/snapshot | Controlled offensive tests |
| AD-DC-01 | AD DS/DNS and synthetic identities | Reusable lab baseline | Identity/AD scenarios |
| WIN-01 | Windows endpoint | Revertible/disposable | Endpoint, identity and detection tests |
| WIN-02 | Optional secondary endpoint | Revertible/disposable | Only when lateral movement or multi-host testing requires it |
| WEB-01 | Vulnerable web/API workload | Rebuildable | Application-security scenarios |
| LINUX-01 | Linux target | Rebuildable | Linux/network/detection scenarios |
| ARES-CTRL | Optional orchestration/evidence service | Persistent only if built | Only after repeated workflows justify automation |

## Operating rule

Do not build or run the whole catalog simply because it exists. A scenario starts the minimum guest set needed to answer the current engineering question.

## Template rules

- Pin OS/version and document image provenance.
- Apply only scenario-relevant vulnerabilities.
- Maintain known-good snapshots where reuse provides value.
- Never use production credentials, personal data, or trusted Cerberus secrets.
- Verify time sync, telemetry, isolation, and reset state before/after exercises.
- Delete disposable targets when retaining them provides no learning or operational value.
