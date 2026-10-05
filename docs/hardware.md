# Hardware Strategy

## Decision

Project Ares has **no dedicated physical hardware**.

The original plan to convert the existing Windows 10-era FX-8320 system into Ares v1 is cancelled. The planned purpose-built Ares v2 system is also cancelled. That PC is now unassigned reusable hardware outside the Ares project.

## Host platform

Ares is an on-demand virtual subsystem of **Project Cerberus**.

Ares may consume Cerberus CPU, memory, storage, and networking while a lab is active, but Ares does not independently justify hardware purchases. Cerberus upgrades must make sense for the workstation's broader Security Engineering, AI Engineering, Oberon, development, and virtualization workloads.

## Capacity policy

- Start with the Cerberus hardware already selected for the broader workstation.
- Run only the VMs required for the current scenario.
- Measure memory, CPU, and storage pressure before adding capacity.
- Additional RAM or VM storage may be useful later, but is not an Ares prerequisite.
- No rack chassis, Ares motherboard, Ares CPU, Ares PSU, dedicated Ares GPU, or dedicated Ares networking purchase is planned.

## Storage

Ares VM images and snapshots may eventually benefit from a separate Cerberus NVMe, but this is a future optimization based on actual usage. It is not required to establish the project.

## Retired hardware plan

The former Ares v1 PC is explicitly outside the COC architecture. It may be stored, sold, donated, used for parts, or repurposed for an unrelated project if a genuine need or fun use appears.
