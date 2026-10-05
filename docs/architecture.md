# Architecture

## Design principles

- **Virtual by design:** Ares is a logical subsystem hosted on Cerberus, not a separate physical computer.
- **Isolation first:** range traffic is denied access to trusted Cerberus services, the home LAN, and the Internet by default.
- **On demand:** create or start only the guests required for the current engineering question.
- **Reproducibility:** useful scenarios define prerequisites, expected telemetry, cleanup, and reset validation.
- **Minimum complexity:** automation, dashboards, and persistent services are added only when they solve a demonstrated problem.
- **Fail safe:** a range can be disconnected or stopped without depending on a target guest.

## Logical planes

| Plane | Components | Purpose |
|---|---|---|
| Host | Cerberus + virtualization layer | Trusted host administration |
| Control | Optional ARES-CTRL / scenario definitions | Orchestration when justified |
| Exercise | Kali, AD, Windows, web and Linux guests | Controlled security testing |
| Evidence | Atlas/Wazuh telemetry, reports, artifacts | Detection validation and learning evidence |

## Trust boundary

The hypervisor/virtualization layer is the boundary between trusted Cerberus workloads and Ares. Ares networks are deny-by-default. Any path to Atlas/Wazuh is explicit, narrow, temporary where practical, and documented. Ares guests receive no trusted Cerberus credentials, shared personal data, or unrestricted host integration.

Ares is suitable for controlled training attacks and intentionally vulnerable lab systems. It is not the place to execute genuinely unknown live malware on the trusted Cerberus host.

## Mission lifecycle

`DEFINE → PREFLIGHT → START REQUIRED GUESTS → VALIDATE ISOLATION → TEST → COLLECT → REMEDIATE → RETEST → RESET/DESTROY → VERIFIED`

The process is intentionally lighter than the original standalone Ares design. Formal mission machinery is only implemented when repeated use demonstrates that it is valuable.

## Resource model

Cerberus resources are shared with normal engineering and AI workloads. Ares therefore runs only the smallest guest set needed for the current exercise. Resource upgrades are justified by measured Cerberus workload pressure, not by a separate Ares hardware roadmap.
