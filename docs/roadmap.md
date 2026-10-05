# Roadmap

## Project decision — October 5, 2026

Ares was redesigned from a dedicated physical cyber-range system into an **on-demand virtual range hosted on Cerberus**.

Cancelled:

- Ares v1 conversion of the existing Windows 10-era PC
- Ares v2 purpose-built hardware
- Proxmox-as-a-dedicated-Ares-host requirement
- large permanent guest fleet
- requirement to complete every planned offensive-security lab

## Phase 1 — establish the virtual boundary

- [ ] Select the Cerberus virtualization stack as part of the Cerberus build
- [ ] Create an isolated Ares virtual network
- [ ] Validate deny-by-default access to trusted Cerberus services and the home LAN
- [ ] Create a reusable Kali attacker VM/template
- [ ] Define snapshot/reset procedure
- [ ] Validate an explicit telemetry path to Atlas/Wazuh

## Phase 2 — first engineering validation

- [ ] Choose one real Security Engineering question
- [ ] Create only the target VM(s) needed for that question
- [ ] Capture baseline telemetry
- [ ] Perform the controlled test
- [ ] Investigate the resulting telemetry/detection
- [ ] Improve the relevant control or detection
- [ ] Retest and document the result
- [ ] Reset or destroy disposable lab state

## Later — only when usage proves value

- [ ] Add reusable AD range components
- [ ] Add web/API or Linux targets when a project needs them
- [ ] Add ARES-CTRL orchestration if repetitive setup/reset work justifies it
- [ ] Add scenario scoring/history if it improves detection-engineering work
- [ ] Add a dashboard only if it provides operational value
- [ ] Consider dedicated Cerberus VM storage if measured I/O pressure warrants it

## Explicit non-goals

- Building a separate Ares computer
- Building Ares v2 hardware
- Completing every pentesting or adversary-emulation lab available
- Maintaining vulnerable VMs that are not being used
- Turning the project into a malware-research platform
- Buying hardware solely to expand Ares

Ares remains a supporting capability for Security Engineering, not a separate specialization.
