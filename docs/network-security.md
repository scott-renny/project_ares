# Network and Security Design

## Virtual zones

| Zone | Typical members | Default policy |
|---|---|---|
| Host/Management | Cerberus virtualization management | Trusted host only |
| Operator | ATTACK-01 | Exercise networks only |
| Exercise | Windows/Linux/AD targets | No trusted LAN access |
| DMZ-Lab | WEB-01 | No WAN exposure; scenario-specific access |
| Telemetry | Explicit path toward Atlas/Wazuh | Send only required telemetry |

## Default isolation

Ares virtual networks are isolated from the normal home LAN and trusted Cerberus services by default. Bridging a vulnerable guest directly onto the trusted LAN is not part of the design.

Internet access is denied by default. If a lab genuinely requires egress, it must be deliberately enabled for the minimum necessary scope and removed afterward.

## Atlas/Wazuh integration

Detection-validation scenarios may need telemetry to reach Atlas/Wazuh. That path is a deliberate exception, not general network membership. Permit only the protocols/destinations required for the test and document the boundary.

## Host integration

Ares guests must not receive:

- personal or production credentials;
- trusted SSH keys;
- unrestricted shared folders;
- personal files;
- automatic access to Cerberus services;
- persistent access to Atlas storage.

Convenience features that weaken the boundary should remain disabled unless a specific low-risk exercise justifies them.

## Emergency containment

The primary containment action is to disconnect or stop the Ares virtual network/guests from Cerberus. Evidence may be captured first when safe. The response must not depend on a potentially compromised target VM.

## Secrets

Use synthetic lab identities and least-privilege test credentials. Repository examples contain placeholders only. Credentials used in credential-access exercises are disposable.

## Malware boundary

Ares is for controlled attack simulation and intentionally vulnerable lab systems. Unknown live malware is outside scope because Cerberus remains a trusted workstation.
